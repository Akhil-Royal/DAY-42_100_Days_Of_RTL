# DAY-42_100_Days_Of_RTL
//Prime Numbers Detector

//DESIGN CODE
module even_detector (
    input [7:0] num,
    output reg is_even
);
    always @(*) begin
        is_even = (num % 2 == 0) ? 1 : 0;
    end
endmodule

////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
//TEST BENCH CODE
module tb_even_detector;
    reg [7:0] test_num;
    wire is_even;
    
    even_detector uut (
        .num(test_num),
        .is_even(is_even)
    );
    
    initial begin
        $monitor("Time=%0t, Number=%d, Is_Even=%b", $time, test_num, is_even);
        
        test_num = 1; #10;
        test_num = 2; #10;
        test_num = 3; #10;
        test_num = 4; #10;
        test_num = 5; #10;
        test_num = 6; #10;
        test_num = 7; #10;
        test_num = 8; #10;
        test_num = 9; #10;
        test_num = 10; #10;
        
        $stop;
    end
endmodule
