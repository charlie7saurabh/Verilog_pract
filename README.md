# Verilog_pract
"A collection of basic Verilog codes for beginners, covering fundamental concepts and examples in digital design. Perfect for students and enthusiasts learning Verilog HDL."

# INVERTER CODE
Verilog Design Code
module jinverter(y,a);
	output y;
	input a;
	
	assign y=~a;
	
endmodule
# INVERTER Testbench CODE

module jinvertertb;
  reg a;
  wire y;

  //Design Instance
  jinverter jinv(y,a);
  
	initial
	begin
		$display ("RESULT\ta\ty");

		a = 1; # 100; // Another value
		if ( y == 0 ) // Test for inversion
			$display ("  PASS  \t%d\t%d",a,y);
		else
			$display ("  FAIL \t%d\t%d",a,y);

		a = 0; # 100; // Initial value is set
		if ( y == 1 ) // Test for inversion
			$display ("  PASS  \t%d\t%d",a,y);
		else
			$display ("  FAIL  \t%d\t%d",a,y);

		a = 1; # 50; // Another value
		if ( y == 0 ) // Test for inversion
			$display ("  PASS  \t%d\t%d",a,y);
		else
			$display ("  FAIL  \t%d\t%d",a,y);

		a = 0; # 100; // Initial value is set
		if ( y == 1 ) // Test for inversion
			$display ("  PASS  \t%d\t%d",a,y);
		else
			$display ("  FAIL  \t%d\t%d",a,y);

	end
  
  //enabling the wave dump
  initial begin 
    $dumpfile("dump.vcd"); $dumpvars;
  end
endmodule
 
