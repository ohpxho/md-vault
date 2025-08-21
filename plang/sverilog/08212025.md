SystemVerilog Notes - Aug 21, 2025
===

## What is HDL?
- Hardware Description Language
- A programming language for describing the structure and behavior of electronic circuits

## What is SystemVerilog?
- Describe circuits
- A superset of Verilog with better RTL coding contructs and added OOP+assertion+contained randomization
- An industry standard for verfication (UVM)

## What is UVM?
- standardized methodology for verifying integrated circuit designs

## What is FPGA?
- Field Programmable Gate Arrays
- A chip
- Logic can be customized for a specific application but can be reprogrammed into another

## What is ASIC?
- Application-Specific Integrated Circuit
- A chip
- Processes data for one application - hardwired
- They are unchangeable once manufactrured - unprogrammable
- Faster that FPGA due to it's optimized to a specific application

`FPGA and ASIC both do not need software`

## Half Adder implementation
- Since halfadder operated on two bits, it's easy to implement
```
module halfadder(
	logic a, b
  	logic sum, carry
);
  assign sum = a ^ b;
  assign carry = a & b;
endmodule
```

- `module` is a block of code similar to a function or class
- `logic` is a data type equivalent to reg or wire in verilog
- `^` is an XOR operation while `&` is an AND operation
- the parameters in the module (enclosed within parenthesis) are called **ports** 

