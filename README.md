# Write-a-program-to-convert-a-natural-number-in-factor-10-to-any-number-in-base-B-1-B-32-.-Sup
Write a program to convert a natural number in factor 10 to any number in base B (1 &lt;= B &lt;= 32). Suppose the base system to be converted is 2 &lt;= B &lt;= 16. The number representing the base system B > 10 is A = 10, B = 11, C = 12, D = 13, E = 14, F = 15 .
package vn.viettuts.baitap;
 
import java.util.Scanner;
 
public class ConvertNumber {
    public static final char CHAR_55 = 55;
    private static Scanner scanner = new Scanner(System.in);
  
    /**
     * main
     * 
     * @author viettuts.vn
     * @param args
     */
    public static void main(String[] args) {
        System.out.print("Nhập số nguyên dương n = ");
        int n = scanner.nextInt();
        System.out.println("So " + n + " trong he co so 2 = "
                + ConvertNumber.convertNumber(n, 2));
        System.out.println("So " + n + " trong he co so 16 = "
                + ConvertNumber.convertNumber(n, 16));
    }
      
    /**
     * chuyen doi so nguyen n sang he co so b
     * 
     * @author viettuts.vn
     * @param n: so nguyen
     * @param b: he co so
     * @return he co so b
     */
    public static String convertNumber(int n, int b) {
        if (n < 0 || b < 2 || b > 16 ) {
            return "";
        }
          
        StringBuilder sb = new StringBuilder();
        int m;
        int remainder = n;
          
        while (remainder > 0) {
            if (b > 10) {
                m = remainder % b;
                if (m >= 10) {
                    sb.append((char) (CHAR_55 + m));
                } else {
                    sb.append(m);
                }
            } else {
                sb.append(remainder % b);
            }
            remainder = remainder / b;
        }
        return sb.reverse().toString();
    }
}
