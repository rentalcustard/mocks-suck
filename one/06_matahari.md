!SLIDE
# Test Spies #
# Matahari #

    @@@ruby
    helper = spy(:helper)

    helper.message(1)

    helper.should have_received.message(1)
