### 5-3,4
```

package test1234;
import java.util.*;

abstract class Converter{
	abstract protected double convert(double src);
	abstract protected String getSrcString();
	abstract protected String getDestString();
	protected double ratio;
	
	public void run() {
		Scanner scanner = new Scanner(System.in);
		System.out.println(getSrcString() + "을 " + getDestString() + "로 바꿉니다.");
		System.out.print(getSrcString() + "을 입력하세요>> ");
		double val = scanner.nextDouble();
		double res = convert(val);
		System.out.println("변환 결과: " + res + getDestString()+ "입니다");
		scanner.close();
	}
}

class Won2Dollar extends Converter{
	public Won2Dollar(int dollor) {
		this.ratio = dollor;
	}
	
	protected String getSrcString() {
		return "원";
	}
	protected String getDestString() {
		return "달러";
	}
	protected double convert(double src) {
		double a = src / ratio;
		return a;
	}
}
class Km2Mile extends Converter{
	public Km2Mile(double a) {
		this.ratio = a;
	}
	
	protected String getSrcString() {
		return "Km";
	}
	protected String getDestString() {
		return "mile";
	}
	protected double convert(double src) {
		double a = src / ratio;
		return a;
	}
}

public class test1 {
	public static void main(String[] arg) {
		//Won2Dollar toDollar = new Won2Dollar(1200);
		//toDollar.run();
		Km2Mile toMile = new Km2Mile(1.6);
		toMile.run();
	}
}

```


### 5-5

```

package test1234;
import java.util.*;

class Point{
	private int x, y;
	public Point(int x, int y) { this.x = x; this.y = y;}
	public int getX() {return x;}
	public int getY() {return y;}
	protected void move(int x, int y) {this.x = x; this.y = y;}
}

class ColorPoint extends Point{
	private String color;
	public ColorPoint(int x, int y, String color) {
		super(x,y);
		this.color = color;
	}
	public void setXY(int x, int y) {
		move(x,y);
	}
	public void setColor(String color) {
		this.color = color;
	}
	public String toString() {
		return color + "색의 (" + getX() + "," + getY() + ")의 점"; 
	}
}

public class test1 {
	public static void main(String[] arg) {
		ColorPoint cp = new ColorPoint(5, 5, "YELLOW");
		cp.setXY(10, 20);
		cp.setColor("RED");
		String str = cp.toString();
		System.out.println(str + "입니다.");
		
	}
}


```

### 5-6

```

package test1234;
import java.util.*;

class Point{
	private int x, y;
	public Point(int x, int y) { this.x = x; this.y = y;}
	public int getX() {return x;}
	public int getY() {return y;}
	protected void move(int x, int y) {this.x = x; this.y = y;}
}

class ColorPoint extends Point{
	private String color;
	public ColorPoint() {
		super(0,0);
		this.color = "BLACK";
	}
	public ColorPoint(int x, int y) {
		super(x,y);
		this.color = "BLACK";
	}
	public ColorPoint(int x, int y, String color) {
		super(x,y);
		this.color = color;
	}
	public void setXY(int x, int y) {
		move(x,y);
	}
	public void setColor(String color) {
		this.color = color;
	}
	public String toString() {
		return color + "색의 (" + getX() + "," + getY() + ")의 점"; 
	}
}

public class test1 {
	public static void main(String[] arg) {
		ColorPoint zeroPoint = new ColorPoint();
		System.out.println(zeroPoint.toString() + "입니다.");
		
		ColorPoint cp = new ColorPoint(10, 10);
		cp.setXY(5,5);
		cp.setColor("RED");
		System.out.println(cp.toString()+ "입니다.");
		
	}
}


```


### 5-7
```

package test1234;
import java.util.*;

class Point{
	private int x, y;
	public Point(int x, int y) { this.x = x; this.y = y;}
	public int getX() {return x;}
	public int getY() {return y;}
	protected void move(int x, int y) {this.x = x; this.y = y;}
}

class ColorPoint extends Point{
	private String color;
	public ColorPoint() {
		super(0,0);
		this.color = "BLACK";
	}
	public ColorPoint(int x, int y) {
		super(x,y);
		this.color = "BLACK";
	}
	public ColorPoint(int x, int y, String color) {
		super(x,y);
		this.color = color;
	}
	public void setXY(int x, int y) {
		move(x,y);
	}
	public void setColor(String color) {
		this.color = color;
	}
	public String toString() {
		return color + "색의 (" + getX() + "," + getY() + ")의 점"; 
	}
}

class Point3D extends Point{
	private int z;
	public Point3D(int x, int y, int z) {
		super(x,y);
		this.z = z;
	}
	public void moveUp() {
		this.z = this.z + 1;
	}
	public void moveDown() {
		this.z = this.z - 1;
	}
	public void move(int x, int y , int z) {
		move(x,y);
		this.z = z;
	}
	public int getZ() {return z;}
	public String toString() {
		return "(" + getX() + "," + getY() + "," + getZ() + ")의 점";
	}
}
public class test1 {
	public static void main(String[] arg) {
		Point3D p = new Point3D(1,2,3);
		System.out.println(p.toString() + "입니다.");
		
		p.moveUp();
		System.out.println(p.toString()+ "입니다.");
		
		p.moveDown();
		p.move(10,10);
		System.out.println(p.toString() + "입니다.");
		
		p.move(100, 200, 300);
		System.out.println(p.toString() +"입니다.");
		
	}
}

```


### 5-8

