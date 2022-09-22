
### 4-1 Code
```
package mytest;
import java.util.Scanner;

	class Menu{
		private int id;
		private String name;
		private double price;
		
		public Menu(int id, String name, double price) {
			this.id = id;
			this.name = name;
			this.price = price/1000;
		};
		
		public Menu() {};
		
		public void setter( int id, String name, double price) {
			this.id = id;
			this.name = name;
			this.price = price/1000;
		}
		
		public Menu getter() {
			return this;
		}
		
		public void print() {
			System.out.println(id + ": " + name + " [" + price + "]");
		}
		
		
	}
	
	
	class Menuboard {
		
		static String[] menus = {"Americano", "Latte", "Mocca", "Cappuccino",
	            "Milk Tea", "Chi Tea", "Lemon Sweet", "Jamong Honey"};

	    static int[] prices = {4100, 4300, 4300, 4800, 5100, 5300, 5800, 6100};
	    
	    private Menuboard() {};
	    
	    static Menu [] c = new Menu[8];
	    
	    public static Menuboard makeBoard(){
	    	Menu [] a = new Menu[8];
	    	Menuboard b = new Menuboard();
	    	for(int i = 0 ; i < 8 ; i ++) {
	    		c[i] = new Menu(i+1 , menus[i], prices[i]);
	    	}
			return b;
	   }
	
	    public void print() {
	    	System.out.println("***** Best Coffee *****");
	    	for(int i = 0 ; i < 8 ; i++) {
		    	c[i].print();
	    	}
	    	System.out.println("***********************");
	    }
	}
	/*
	class Order{
		
	}
	
	class MenuOrder{
		
	}
	
	
	*/
	
	public class test1 {
		public static void main(String[] args) {
	        Menuboard mboard = Menuboard.makeBoard();
	        mboard.print();
	    }
}

```
