# DAY-42_100_Days_Of_RTL
//Prime Numbers Detector

//DESIGN CODE
module prime_detector (
    input [7:0] num,
    output reg is_prime
);
    integer i, count;
    always @(*) begin
        count = 0;
        for (i = 1; i <= num; i = i + 1) begin
            if (num % i == 0)
                count = count + 1;
        end
        is_prime = (count == 2) ? 1 : 0;
    end
endmodule

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
//TEST BENCH CODE
module tb_prime_detector;
    reg [7:0] test_num;
    wire is_prime;
    
    prime_detector uut (
        .num(test_num),
        .is_prime(is_prime)
    );
    
    initial begin
        $monitor("Time=%0t, Number=%d, Is_Prime=%b", $time, test_num, is_prime);
        
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

