
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
		}package testest;
import java.util.*;

public class test
{
    public static int[][] makeArray(Scanner s) {
        //출력 결과를 참고하여 사용자로부터 정방형 배열 크기("array size? ")를 입력받고 배열을 생성한다. 
    	int p = 0;
    	System.out.print("array size? ");
    	int a = s.nextInt();
    	int i [][] = new int[a][];
    	for(int k = 0 ; k <a ; k++) {
    		i[k] = new int[a-k];
    	}
    	
    	for(int j = 0 ; j < a ; j++) {
    		p = j;
    		for(int k = 0 ; k < i[j].length ; k++) {
    			i[j][k] = p;
    			p++;
    		}
    	}
    	/*for(int j = 0 ; j < a ; j++) {
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
    	*/
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

### 3-2 연습

```
package testest;
import java.util.*;

public class test
{
    public static int[][] makeArray(Scanner s) {
        //출력 결과를 참고하여 사용자로부터 정방형 배열 크기("array size? ")를 입력받고 배열을 생성한다. 
    	int p = 0;
    	System.out.print("array size? ");
    	int a = s.nextInt();
    	int i [][] = new int[a][];
    	for(int k = 0 ; k <a ; k++) {
    		i[k] = new int[a-k];
    	}
    	
    	for(int j = 0 ; j < a ; j++) {
    		p = j;
    		for(int k = 0 ; k < i[j].length ; k++) {
    			i[j][k] = p;
    			p++;
    		}
    	}
    	/*for(int j = 0 ; j < a ; j++) {
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
    	*/
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


### 5-1

```

[5장 실습용 문제]

/******************************************************************************
 * 문제 5-1
 ******************************************************************************/
// 새로운 프로젝트를 만든 후 새로운 클래스 Main를 만들어 Main.java 소스파일을 만들어라.
// 그런 후 아래 소스코드를 복사해 소스파일에 삽입하라.
//
// main()에서 Manager 클래스의 객체 manager를 생성한 후 
// 이 manager 객체에 Line과 Circle의 그래픽 객체들을 삽입한다.
// manager는 linked list로 모든 그래픽 객체들을 관리하며
// display()를 통해 manager에 삽입된 모든 객체들을 화면에 보여주고 
// move() 메소드를 통해 모든 그래픽 객체들의 좌표를 이동한다.
//
// 구현할 사항: Shape를 상속한 Line, Circle 클래스를 구현하라.
//           또한 Manager::add(Shape s)를 구현하라.
//
//=============================================================================

// 경고: 아래 각 클래스의 멤버 변수는 더 이상 추가하지 말고 
// 기존 멤버의 접근지정자도 수정하지 말것.


// 화면상의 한 점의 좌표를 저장하며 이 점의 좌표를 출력하거나 이동하여 주는 클래스 
class Point {
    private int x, y; // 점의 좌표
    
    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
    public void display() {  // 좌표 출력
        System.out.print("("+x+","+y+")");
    }
    public void move(int width, int height) { // 좌표 이동
        x += width;  y += height;
    }
}

// Shape 추상 클래스 선언 
abstract class Shape {
    private int thick;       // 선의 두께
    private String color;    // 선의 색깔
    public Shape next;       // Lined list에서 다음 shape의 참조자
    
    public Shape(int thick, String color) {
        next = null;
        this.thick = thick;
        this.color = color;
    }
    public void display() {  // 그래픽 정보 출력
        System.out.print("("+thick+","+color+")");
    }
    public abstract void move(int width, int height); // 좌표 이동
}

문제: Shape 클래스 상속하여 Line 클래스를 작성하라.
class Line { 
    private Point p1, p2; // 두 점의 좌표
    
    public Line(int thick, String color, Point p1, Point p2);
    생성자 및 필요한 멤버 메소드 구현
}

문제: Shape 클래스 상속하여 Circle 클래스를 작성하라.
class Circle {
    private Point center;    // 중심점
    private int radius;      // 반지름
    
    public Circle(int thick, String color, Point center, int radius);
    생성자 및 필요한 멤버 메소드 구현
}

// add() 함수를 통해 추가된 그래픽 객체들을 linked list로 관리한다.
class Manager {
    Shape first, last; // Shape의 linked list의 시작과 끝을 참조함
    
    public Manager() {
        first = last = null;
    }
    
    public void add(Shape s) {

        문제: linked list의 마지막 원소(last) 뒤에 그래픽 객체 s를 추가하라. 
       
    }
    public void display() { // linked 리스트의 모든 그래픽 객체를 출력한다.
        for (Shape s = first; s != null; s = s.next)
            s.display();
    }

    // 그래픽 객체의 이동할 width, height는 사용자로부터 직접 입력 받은 후
    // linked 리스트의 모든 그래픽 객체의 좌표를 width, height 만큼 이동한다.
    public void move(Scanner in) {
        System.out.print("width and height to move? ");
        int width  = in.nextInt();
        int height = in.nextInt();
        for (Shape s = first; s != null; s = s.next)
            s.move(width, height);
        display();
    }
}

public class Main {
    // 그래픽 객체를 미리 생성하여 배열에 저장해 둠.
    static private Shape[] shapes = {
            new Line(0, "BLACK", new Point(10, 11), new Point(20, 21)),
            new Line(1, "WHITE", new Point(30, 31), new Point(40, 41)),
            new Circle(2, "RED", new Point(50, 51), 10),
            new Circle(3, "RED", new Point(50, 51), 10),
    };

    public static void main(String[] args) 
    {
        Scanner in = new Scanner(System.in);
        // Manager의 linked 리스트에 처음으로 삽입할 그래픽 객체 배열 인덱스를 입력 받음
        System.out.print("begin index(0~4) of shapes array? ");
        int beg  = in.nextInt();

        Manager manager = new Manager();
        // 입력 받은 배열 인덱스(beg)부터 순서적으로 Manager에 추가함
        for(int count = 0; count < shapes.length; count++, beg = ++beg % 4)
            manager.add(shapes[beg]);

        manager.display();
        
        while(true) {
            System.out.print("\n0.exit 1.display 2.move >> ");
            int input = in.nextInt(); // 메뉴를 보여 주고 메뉴 항목을 입력 받음
            if (input == 0)
                break;
            switch (input) {
            case 1: manager.display();       
                    break;
            case 2: manager.move(in);    
                    break;
            }
        }
        in.close();
    }
}

===============================================================================
== [문제 5-1] 실행 결과
===============================================================================    
begin index(0~4) of shapes array? 3
C(3,RED)(50,51):10        // 원의 경우: C(두께,색깔)(중심점x,y좌표):반지름
L(0,BLACK)(10,11)(20,21)  // 선의 경우: L(두께,색깔)(처음점x,y좌표)(두번째점x,y좌표)
L(1,WHITE)(30,31)(40,41)
C(2,RED)(50,51):10

0.exit 1.display 2.move >> 2
width and height to move? 10 10
C(3,RED)(60,61):10
L(0,BLACK)(20,21)(30,31)
L(1,WHITE)(40,41)(50,51)
C(2,RED)(60,61):10

0.exit 1.display 2.move >> 2
width and height to move? 10 10
C(3,RED)(70,71):10
L(0,BLACK)(30,31)(40,41)
L(1,WHITE)(50,51)(60,61)
C(2,RED)(70,71):10

0.exit 1.display 2.move >> 2
width and height to move? -20 -20
C(3,RED)(50,51):10
L(0,BLACK)(10,11)(20,21)
L(1,WHITE)(30,31)(40,41)
C(2,RED)(50,51):10

0.exit 1.display 2.move >> 0

```

```

import java.util.*;

class Point {
    private int x, y; // 점의 좌표
    
    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
    public void display() {  // 좌표 출력
        System.out.print("("+x+","+y+")");
    }
    public void move(int width, int height) { // 좌표 이동
        x += width;  y += height;
    }
}

// Shape 추상 클래스 선언 
abstract class Shape {
    private int thick;       // 선의 두께
    private String color;    // 선의 색깔
    public Shape next;       // Lined list에서 다음 shape의 참조자
    
    public Shape(int thick, String color) {
        next = null;
        this.thick = thick;
        this.color = color;
    }
    public void display() {  // 그래픽 정보 출력
        System.out.print("("+thick+","+color+")");
    }
    public abstract void move(int width, int height); // 좌표 이동
}

//문제: Shape 클래스 상속하여 Line 클래스를 작성하라.
class Line extends Shape  { 
    private Point p1, p2; // 두 점의 좌표
    
    @Override
    public void move(int width, int height) {
    	// TODO Auto-generated method stub
    	p1.move(width, height);
    	p2.move(width, height);
    }
    public Line(int thick, String color, Point p1, Point p2) {
    super(thick, color);
    this.p1 = p1;
    this.p2 = p2;
    }
    //생성자 및 필요한 멤버 메소드 구현
}

//문제: Shape 클래스 상속하여 Circle 클래스를 작성하라.
class Circle extends Shape {
    private Point center;    // 중심점
    private int radius;      // 반지름
    
    @Override
    public void move(int width, int height) {
    	// TODO Auto-generated method stub
    	center.move(width, height);
    }
    public Circle(int thick, String color, Point center, int radius) {
    //생성자 및 필요한 멤버 메소드 구현
    	super(thick, color);
    	this.center = center;
    	this.radius = radius;
    }
}

// add() 함수를 통해 추가된 그래픽 객체들을 linked list로 관리한다.
class Manager {
    Shape first, last; // Shape의 linked list의 시작과 끝을 참조함
    
    public Manager() {
        first = last = null;
    }
    
    public void add(Shape s) {

        //문제: linked list의 마지막 원소(last) 뒤에 그래픽 객체 s를 추가하라. 
       if(last != null) {
    	   last.next =s;
       }
       last =s;
    		   
    }
    public void display() { // linked 리스트의 모든 그래픽 객체를 출력한다.
        for (Shape s = first; s != null; s = s.next)
            s.display();
    }

    // 그래픽 객체의 이동할 width, height는 사용자로부터 직접 입력 받은 후
    // linked 리스트의 모든 그래픽 객체의 좌표를 width, height 만큼 이동한다.
    public void move(Scanner in) {
        System.out.print("width and height to move? ");
        int width  = in.nextInt();
        int height = in.nextInt();
        for (Shape s = first; s != null; s = s.next)
            s.move(width, height);
        display();
    }
}

public class TEST1 {
    // 그래픽 객체를 미리 생성하여 배열에 저장해 둠.
    static private Shape[] shapes = {
            new Line(0, "BLACK", new Point(10, 11), new Point(20, 21)),
            new Line(1, "WHITE", new Point(30, 31), new Point(40, 41)),
            new Circle(2, "RED", new Point(50, 51), 10),
            new Circle(3, "RED", new Point(50, 51), 10),
    };

    public static void main(String[] args) 
    {
        Scanner in = new Scanner(System.in);
        // Manager의 linked 리스트에 처음으로 삽입할 그래픽 객체 배열 인덱스를 입력 받음
        System.out.print("begin index(0~4) of shapes array? ");
        int beg  = in.nextInt();

        Manager manager = new Manager();
        // 입력 받은 배열 인덱스(beg)부터 순서적으로 Manager에 추가함
        for(int count = 0; count < shapes.length; count++, beg = ++beg % 4)
            manager.add(shapes[beg]);

        manager.display();
        
        while(true) {
            System.out.print("\n0.exit 1.display 2.move >> ");
            int input = in.nextInt(); // 메뉴를 보여 주고 메뉴 항목을 입력 받음
            if (input == 0)
                break;
            switch (input) {
            case 1: manager.display();       
                    break;
            case 2: manager.move(in);    
                    break;
            }
        }
        in.close();
    }
}


```
