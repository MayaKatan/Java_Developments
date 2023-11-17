/**
 * The class Ex12 is divided into 3 methods. 
 * The methods return the following results:
 * 
 * Q1 (firs method): returns the length of the longest sequence of identical digits found in it. 
 * Q2 (Second method): the method returns a subnumber of num that all his digits are divisible by the digit we defined.
 * Q3 (The third method): A method that accepts an integer as a parameter n, and returns TRUE if the number is a special number and FALSE otherwise. 
 *
 * @Author (Maya Katan)
 * @Date 17.12.2022
 */
public class Ex12
{
    /**
     * Question 1:
     *
     * A method which accepts a positive integer num, and returns the length of the 
     * longest sequence of identical digits found in it.
     * 
     * @param num  The number which is tested by its longest sequence of identical digits
     * 
     * @return  The longest sequence of identical digits in the number
     */
    public static int equalDigits (int num){
        return equalDigits(num,1,1);      
    } 
    /**
     * Auxiliary method for Question 1.
     * 
     * @param num  The number which is tested by its longest sequence of identical digits 
     * @param count  Counting a length of a sequence of identical digits
     * @param maxCount  The length of the longest identical digits which has been counted
     * 
     * @return  The longest sequence of identical digits in the number
     */
    private static int equalDigits(int num, int count, int maxCount){
        int unity = num%10, dozens = (num/10)%10;
        if(count > maxCount ){
                maxCount = count;
        }
        if(num < 10){ //stop conditions
            return maxCount;
        }
        if(unity == dozens){ //When the ones digit is the same as the tens digit
             equalDigits(num/10, count++, maxCount) ;
        }
        else if(unity != dozens){ //When the ones digit is NOT the same as the tens digit
            count = 1;
        }
        return equalDigits(num/10, count, maxCount) ;         
    }
    
    /**
     * Question 2:
     *
     * The method accepts as a parameter a natural number (num) and digit.
     * the method returns a subnumber of num that all his digits are divisible by the digit we defined.
     * the returned value keeps the order of the digits as in the original number
     * 
     * @param num  The input number which its digits tested to be divisible by the input digit
     * @param digit  The input digit which is divided by number's digits
     * 
     * @return  The sub number of the input number which its digits are divisible by the digit we defined
     */
    public static int subNumber (int num, int digit) {
        if(num%10 == 0) // the unit of the number is 0
            return subNumber (num/10, digit, 0,10); 
        return subNumber(num, digit, 0, 1);
    }
    /**
     * Auxiliary method for Question 2.
     * 
     * @param num  The input number which its digits tested to be divisible by the input digit
     * @param digit  The input digit which is divided by number's digits
     * @param sub  The created sub number of the input number that will be returned
     * @param subCounter  The counter of the sub number's digits which is used to create the sub number
     * 
     * @return  The sub number of the input number which its digits are divisible by the digit we defined
     */
    private static int subNumber (int num, int digit, int sub,int subCounter) {
        int unit = num%10; // the number's unit
        
        if(num < 10) { // the number's first digit 
            if(num % digit == 0 && subCounter >= 10) { // the sub number's first digit equals to the number's first digit
                return sub += unit*subCounter;
            }
            else if(num % digit == 0 && subCounter < 10) // the sub number is the number's first digit
                return sub += unit;
            else    // the number's first digit isn't exist in the sub number
                return sub;
        }
        
        
        if(unit%digit == 0) { // the number's unit is divisible by the digit's value
            if(subCounter >= 10) { // another unit that can be divided
                sub += unit*subCounter;
                subCounter*= 10;
            }
            else { // the first time a unit can be divided
                subCounter *= 10;
                sub = unit;
            }
        }
        
        // cuts the number's unit
        return subNumber(num/10, digit, sub, subCounter);
    }
    
    /**
     * Question 3:
     *
     * A method which accepts an integer as a parameter n, and returns TRUE if the number is a special number and FALSE otherwise
     * The definition for a special number is: A number that remains part of a group,
     * even after we performed a permanent deletion according to legality.
     * The legality (defined in the method as skipping) is an ascendant legality starting from digit 2.
     * 
     * @param n  The number which is tested if its a special number
     * 
     * @return  TRUE if the number is special, else returns FALSE
     */
    public static boolean isSpecial (int n){
        return isSpecial(n,2);   
    }
    /**
     * Auxiliary method for Question 3.
     * 
     * @param n  The number which is tested if its a special number 
     * @param skipping  The legality
     * 
     * @return  TRUE if the number is special, else returns FALSE
     */
    private static boolean isSpecial (int n, int skipping){
        if(n == 1){ //edge case
            return true;
        }
        if(skipping > n || n % skipping != 0){ //When the number is defined as a special number
            isSpecial(n - (n/skipping), skipping++); //based on mathematical regularity
            return true; 
        }
        else{ //When the number is NOT defined as a special number
            return false; 
        }
    }
} //End of class Ex12.
