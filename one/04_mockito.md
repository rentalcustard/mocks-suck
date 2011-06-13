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
      Helper helper = mock(Helper.class);

      helper.message();

      verify(helper).message();
    }
