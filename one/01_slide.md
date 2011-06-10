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

