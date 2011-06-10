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
