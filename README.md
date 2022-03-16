# -
这是个测试
Integer.toString(i).equals(new StringBuffer(Integer.toString(i)).reverse().toString())
import java.util.Scanner;



public class test_one{
	public static void main(String[] args) {
		Scanner input=new Scanner(System.in);
		String str=input.next();
		String numPinYin[]= {"ling","yi","er","san","si","wu","liu","qi","ba","jiu"};
		String[] digitPinYin = {"", "", "shi", "bai", "qian", "wan", "shi", "bai", "qian", "yi", "shi"};
        String[] digitPinYin2 = {"", "", "shi", "bai", "qian", "wan", "shi wan", "bai wan", "qian wan", "yi", "shi yi"};
        char[] charArray=str.toCharArray();
        int lenth=charArray.length;//get length
        for (int i = 0; i < lenth; i++) {
			int j=str.charAt(i)-'0';//get digit
			if(j==0) {//print 0 yes or no
				if(i<lenth-1 && charArray[i+1]!='0')System.out.println("ling");// Add '0' when from digit to digit exists 0
			}
			else {
				boolean b=i<lenth-3 && charArray[i+1]=='0' && charArray[i+2]=='0' &&charArray[i+3]=='0';//at least have 3 char is 0
				
				if((lenth-i==2||lenth-i==6 ||lenth-i==10) &&j==1 &&i==0) {
					if(b)System.out.print(digitPinYin2[lenth-i]+" ");
					else System.out.print(digitPinYin[lenth-i]+" ");
				}else {
					if(b)System.out.print(numPinYin[j]+" "+digitPinYin2[lenth-i]+" ");
					else System.out.print(numPinYin[j]+" "+digitPinYin[lenth-i]+" ");
					
				}
			}
		}
	}
}
