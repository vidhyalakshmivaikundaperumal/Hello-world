# Hello-world
My repository on github
package Finalexam;
/**
 * 
 *Exception Errorcode inhertance the labzero
 *  and lab1
 *
 */

class ErrorCode extends Exception {
	   private int code;
	   public ErrorCode(int i1){code = i1; }
	   public int getCode() { return code; }
	}
/**
 * 
 *LabZero  is extends to Errorcode
 *
 */
	class LabZero extends ErrorCode {
	   public LabZero() {super(1); }
	}
	/**
	 * 
	 * lab1 is extends form Errorcode
	 * constructor
	 *
	 */
	class Lab1 extends ErrorCode{
		private int i;
		public Lab1(int i1){super(2); i=i1;}
		public int getI(){return i;}
	}
	class Morethan15 extends ErrorCode {
	   private int i;
	   public Morethan15(int i1){super(3); i = i1; }
	   public int getI() { return i; }
	}
	
	class CS480K1Lab {
		   private int week;
		   public CS480K1Lab(int week1)  throws Morethan15,LabZero,Lab1
		   {
		      if (week1 >15)
		         throw new Morethan15(week1);
		      else if (week1 == 0)
		         throw new LabZero();
		      else if(week1==1)
		    	  throw new Lab1(week1);
		      else
		         week=week1;
		   }
		   /**
		    * 
		    * week1
		    *  Morethan15
		    *  LabZero
		    *  Lab1
		    */
		   public void setWeek(int week1) throws Morethan15, LabZero,Lab1
		   {
		      if (week1 > 15)
		         throw new Morethan15(week1);
		      else if (week1 == 0)
		         throw new LabZero();
		      else if(week1 ==1)
		      throw new Lab1(week1);
		      else
		         week= week1;
		   }
		}
	/**
	 * Cs480k1lab
	 * 
	 * @author vidhya (vidhya3sep@gmail.com)
	 *version Dec 10 2014
	 */
	

public class Exam {
	public static void main (String argv[])
	   {
	      
	      try {
	         CS480K1Lab lab = new CS480K1Lab(15);
	         CS480K1Lab lab1 = new CS480K1Lab(2);
	         CS480K1Lab lab2 = new CS480K1Lab(1);
	         
	        }
	      catch (Morethan15 n) {
	         System.out.println("Error " +
	                n.getCode() + ": " +
	                "No lab on week " + n.getI());
	      }
	      catch (LabZero n) {
	         System.out.println("Error " +
	                n.getCode() + ": " +
	                "Error in setting 0");}
	      catch(Lab1 n){
	    	  System.out.println("Error " +
		                n.getCode() + ": " +
		                "No lab on week1 " + n.getI());
		  
	      }
	      
	      
	 finally{
		 System.out.println("end");
	 }
}
}                
