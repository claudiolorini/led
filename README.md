led
===

A test EtherCat/EtherLab based application that turns LEDs on and off (based on EtherLab/examples/user/main.c).

The code here assumes the following setup for the ethercat slaves (`ethercat slaves` command):

  0:0  EK1100
  0:1  EL1252
  0:2  EL2202
  0:3  EL2202
  0:4  EL1252
  0:5  EL2202
  0:6  EL1252

The application sets a timer to run the `cyclic_task()` routine `FREQUENCY` times per second.
This routine should normally check the current input and output states.
A call to `ecrt_master_send(master)` also needs to be made this frequently to avoid a watchdog timeout.
Note that the EL2202 will reset its outputs to 0 after 100ms if not updated.

