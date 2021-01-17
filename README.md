# uvm_messaging_verbosity
Lets take a look at the uvm_verbosity definitions 

# Example 1 
1) Let's run this simulation without any changes. As mentioned, Since the default uvm_verbosity is uvm_medium, we wont see the UVM_HIGH,UVM_FULL,UVM_DEBUG messages in this run.

# Example 2
1) Let's change the UVM_VERBOSITY from command line, add this to the commmand line +UVM_VERBOSITY=UVM_HIGH and rerun the test.
2) We will see UVM_HIGH,UVM_MEDIUM,UVM_LOW,UVM_NONE messages getting printed.

# Example 3
1) Let's say we dont' want to turn on the UVM_HIGH messages for all the components, because it is too verbose. We can use uvm_set_verbosity from the command line to control the messages on specific components.
Here is the Syntax for it.
From UVM 1.2,

// +uvm_set_verbosity=<comp>,<id>,<verbosity>,<phase|time>,<offset>
// +uvm_set_verbosity=uvm_test_top.env0.agent1.*,_ALL_,UVM_FULL,time,800

// Let's rerun the above code with the commmand line option +uvm_set_verbosity=uvm_test_top.env,_ALL_,UVM_DEBUG,connect
// Basically it tells to display all the id's inside UVM_ENV with verbosity UVM_DEBUG in connect phase
