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
 
