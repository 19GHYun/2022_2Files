
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



### 4-2 code

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
		
		public int getid() {
			return id; 
		}
		public String getname() {
			return name;
		}
		public double getprice() {
			return price;
		}
		
		public void print() {
			System.out.println(id + ": " + name + " [" + price + "]");
		}
		
		
	}
	
	
	class Menuboard {
		
		static String[] menus = {"Americano", "Latte", "Mocca", "Cappuccino",
	            "Milk Tea", "Chi Tea", "Lemon Sweet", "Jamong Honey"};

	    static int[] prices = {4100, 4300, 4300, 4800, 5100, 5300, 5800, 6100};
	    
	    Menuboard() {};
	    
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
	
	class Order{
		static int [] menunumber;
		static int [] ordernumber;
		
		static Menuboard a;
		
		int cnt;
		
		Order(int much, Menuboard d) {
			menunumber = new int[much];
			ordernumber = new int[much];
			a = d;
			cnt = 0;
		}
		
		boolean addMenu(int number, int many){
			if((number > 8) || (number < 0)) {
				System.out.println("Menu id " + number + " doesn't exist in our menuboard");
				return false;
			}
			else {
				menunumber[cnt] = number;
				ordernumber[cnt] = many;
				cnt++;
				System.out.println("Your selected menu is added to the order");
				return true;
			}
		}
		void print() {
			System.out.println("** Order details **");
			for(int i = 0 ; i < 4 ; i++) {
				System.out.println("Menu: " + Menuboard.menus[menunumber[i]-1] + " Qty: " + ordernumber[i] + " Price: " + (ordernumber[i])*Menuboard.prices[menunumber[i]-1]);
			}
		}
	}
	
	class MenuOrder{
		private MenuOrder () {};
		static MenuOrder makeOrder(){
			MenuOrder c = new MenuOrder();
			Menuboard mboard = Menuboard.makeBoard();
	        mboard.print();
	        
	        int much;
	        int menuno;
	        int quantity;
	        Scanner s = new Scanner(System.in);
	        System.out.print("How many kinds of drinks? ");
	        much = s.nextInt();

	        Order abc = new Order(much, mboard);
	        
	        for(int i = 0 ; i < 4 ; i++) {
	        	System.out.print("Menu no? ");
	        	menuno = s.nextInt();
	        	System.out.print("Quantity? ");
	        	quantity = s.nextInt();
	        	
	        	if(abc.addMenu(menuno, quantity) == false) {
	        		i--;
	        	}
	        }
	        abc.print();
	        
	        
	        
	        s.close();
	        return c;
		}
	}
	
	
	public class Main {
	    public static void main(String[] args) {
	        MenuOrder.makeOrder();
	    }
	}

