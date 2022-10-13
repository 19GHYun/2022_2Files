
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


### 3장연습문제
```

package testest;
import java.util.*;

public class test
{
    public static int[][] makeArray(Scanner s) {
        //출력 결과를 참고하여 사용자로부터 정방형 배열 크기("array size? ")를 입력받고 배열을 생성한다. 
    	int p = 1;
    	System.out.print("array size? ");
    	int a = s.nextInt();
    	int i [][] = new int[a][a];
    	for(int j = 0 ; j < a ; j++) {
    		for(int k = 0 ; k < a ; k++) {
    			//i[j][k] = p;
    			//p++;
    			if( j + k +1 >= a ) {
    				i[j][k] = p;
    				p++;
    			}
    			else
    				i[j][k] = 0;
    		}
    	}
    	
    	return i;
        //필요한 배열의 원소들을 적절히 초기화한 후 배열을 리턴한다. 
        //(초기화하지 않은 배열 원소는 0으로 자동 설정된다.)
    }

    public static void printArray(int arr[][]) {
        //출력 결과를 참고하여 2차원 배열 arr[][]의 모든 원소들을 출력한다.
    	for(int i = 0 ; i < arr.length; i++ ) {
    		System.out.print("arr[" + i + "] ");
    		for(int k = 0; k < arr[i].length; k++) {
    			System.out.print(arr[i][k] + " ");
    		}
    		System.out.println();
    	}
    }
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int arr[][];
        
        while(true){
        { // 아래 과정을 계속 반복 수행한다.
            arr = makeArray(scanner);
            printArray(arr);
            System.out.print("continue? ");
            //문자열 단어 하나를 입력 받음
            String abc = scanner.next();
            System.out.println();
            //입력된 단어가 "yes"이면 계 close.scanner();속 반복 수행하고 "yes"가 아니면 여기서 반복을 중단한다.
            if(abc.equals("yes")) {
            	continue;
            }
            else
            	break;
        }
        }
 
        //스캐너 객체 닫기;
        scanner.close();
        System.out.println("Done.");
    }
}


```
