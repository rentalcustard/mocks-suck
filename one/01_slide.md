!SLIDE center
# Mocks suck #

!SLIDE
# Testing without mocks #

    @@@ruby
    #Arrange
    my_thing = Thing.new :colour => yellow

    #Act
    my_thing.bleach!

    #Assert
    my_thing.colour.should == white

!SLIDE 
# Mocks mess your mind up #

    @@@ruby

    helper = mock(:helper)
    my_thing = Thing.new :helper => helper
    

    helper.should_receive(:message)
 

    my_thing.do_something_cool 

!SLIDE 
# Mocks mess your mind up #
    @@@ruby
    #Arrange
    helper = mock(:helper)
    my_thing = Thing.new :helper => helper
    
    #Assert
    helper.should_receive(:message)
 
    #Act
    my_thing.do_something_cool 

!SLIDE
# Mocks are paranoid #
    @@@ruby
    #Before
    def do_something_cool
      helper.message
    end

!SLIDE bullets
# Mocks are paranoid #
    @@@ruby
    #After
    def do_something_cool
      helper.message unless helper.inaccessible?
    end

* Now our test fails - "Mock helper received unexpected message 'inaccessible?'"
 
!SLIDE bullets incremental
# Test spies (in Java!) #

* Mockito implements test spies for Java
* Released in 2008
* Better than anything we have in Ruby
* Has a terrible name

!SLIDE
# Test spies (in Java!) #

    @@@java
    public void testStuff() {
      Helper helperSpy = mock(Helper.class);

      helperSpy.message();

      verify(helperSpy).message();
    }

!SLIDE
# RR #

    @@@ruby
    helper = Object.new
    stub(helper).message
    
    helper.message(1)

    helper.should have_received.message(1)


!SLIDE
# RR #

    @@@ruby
    helper = Object.new
    stub(helper).message #Without this line...
    
    helper.message(1) #...This one fails

    helper.should have_received.message(1)

!SLIDE
# Matahari #

    @@@ruby
    helper = spy(:helper)

    helper.message(1)

    helper.should have_received.message(1)

!SLIDE bullets
# Thanks #

* Twitter: @mortice
* tomstuart.co.uk

