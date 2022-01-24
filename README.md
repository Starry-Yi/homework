# homework
1、求和
    public static void main(String[] args) {
        System.out.println("请输入若干个数，每输入一个数回车确认");
        System.out.println("最后输入数字0结束操作");
        Scanner reader = new Scanner(System.in);
        double sum = 0;
        double x = reader.nextDouble();
        while(x != 0){
            sum =  sum+x;
            x = reader.nextDouble();
        }
        System.out.println("sum="+sum);
    }
2、查找数组中的数字
    public static void main(String[] args) {
       int start = 0,end,middle;
       int a[] = {12,45,67,89,123,67,-45};
       int N = a.length;
       for(int i = 0; i < N-1; i++){
       for(int j = i+1; j < N; j++){
       if(a[j] < a[i]){
           int t = a[i];
           a[j] = a[i];
           a[i] = t;
             }
           }
       }
       Scanner scanner=new Scanner(System.in);
       System.out.println("输入整数，程序判断该整数是否在组中");
       int number = scanner.nextInt();
       int count = 0;
       end = N-1;
       middle = (start + end)/2;
       while(number != a[middle]){
           if(number > a[middle])
               start = middle;
           else if(number < a[middle])
               end = middle;
           middle = ( start + end)/2;
           count++;
           if(count>N/2)
               break;
       }
       if(count > N/2)
           System.out.printf("%d不在数组中.\n",number);
       else
           System.out.printf("%d在数组中.\n",number);
    }
3、遍历数组
    public static void main(String[] args) {
      int a[] = {1,2,3,4};
      char b[] = {'a','b','c','d'};
      for(int n = 0;n <a.length;n++){
          System.out.println(a[n]);
      }
      for(int n = 0; n <b.length;n++){
          System.out.println(b[n]);
      }
      for(int i : a){
          System.out.println(i);
      }
      for(char ch: b){
          System.out.println(ch);
      }
    }
4、求和及平均数
    public static void main(String[] args) {
        Scanner reader = new Scanner(System.in);
        double sum = 0;
        int m = 0 ;
        while(reader.hasNextDouble()){
            double x = reader.nextDouble();
            m = m +1;
            sum = sum+x;
        }
        System.out.printf("%d个数的和为%f\n",m,sum);
        System.out.printf("%d个数的平均值为%f\n",m,sum/m);
    }
5、猪八戒娶媳妇
    public static void main(String[] args) {
        XiyoujiRenwu zhubajie,sunwukong;
        zhubajie = new XiyoujiRenwu();
        sunwukong = new XiyoujiRenwu();
        zhubajie.height = 1.8f;
        zhubajie.head = "大头";
        zhubajie.ear = "一双大耳";
        sunwukong.height = 1.62f;
        sunwukong.weight = 1000f;
        sunwukong.head = "秀发飘飘";
        System.out.println("zhubajie的身高:"+zhubajie.height);
        System.out.println("zhubajie的头:"+zhubajie.head);
        System.out.println("sunwukong的重量:"+sunwukong.weight);
        System.out.println("sunwukong的头:"+sunwukong.head);
        zhubajie.speak("俺老猪要取媳妇");
        System.out.println("zhubajie现在的头:"+zhubajie.head);
        sunwukong.speak("老孙重1000斤，我想骗八戒背我");
        System.out.println("sunwukong现在的头:"+sunwukong.head);
    }
6、引用坐标
    public static void main(String[] args) {
       Point p1,p2;
       p1 = new Point();
       p2 = new Point();
       System.out.println("p1的引用:"+p1);
       System.out.println("p2的引用:"+p2);
       p1.setXY(1111, 2222);
       p2.setXY(-100,-200);
       System.out.println("p1的x,y坐标:"+p1.x+","+p1.y);
       System.out.println("p2的x,y坐标:"+p2.x+","+p2.y);
       p1 = p2;
       System.out.println("将p2的引用赋给p1后:");
       System.out.println("p1的引用:"+p1);
       System.out.println("p2的引用:"+p2);
       System.out.println("p1的x,y坐标:"+p1.x+","+p1.y);
       System.out.println("p2的x,y坐标:"+p2.x+","+p2.y);
    }
7、计算圆锥体积
public class Circular {
    Circle bottom;
    double height;
    void setBottom(Circle c){
        bottom = c;
    }
    void setHeight(double h){
        height = h;
    }
    double getVolme(){
        if(bottom == null)
            return -1;
        else 
            return bottom.getArea()*height/3.0;
    }
    double getBottomRadius() {
        return bottom.getRadius();
    }
    public void setBottomRadius(double r){
        bottom.setRadius(r);
    }
}
public class Circle {
    double radius,area;
    void setRadius(double r){
        radius = r;
    }
    double getRadius(){
        return radius;
    }
    double getArea(){
        area = 3.14*radius*radius;
        return area;
    }
}
    public static void main(String[] args) {
        Circle circle = new Circle();
        circle.setRadius(10);
        Circular circular = new Circular();
        System.out.println("circle的引用："+circle);
        System.out.println("圆锥的bottom的引用："+circular.bottom);
        circular.setHeight(5);
        circular.setBottom(circle);
        System.out.println("circle的引用："+circle);
        System.out.println("圆锥的bottom的引用："+circular.bottom);
        System.out.println("圆锥的体积:"+circular.getVolme());
        System.out.println("修改circle的半径，bottom的半径同样变化");
        circle.setRadius(20);
        System.out.println("bottom的半径："+circular.getBottomRadius());
        System.out.println("重新创建circle,circle的引用将发生变化");
        circle = new Circle();
        System.out.println("circle的引用："+circle);
        System.out.println("但不影响circular的bottom的引用");
        System.out.println("圆锥的bottom的引用："+circular.bottom);
    }
8、手机号码
public class SIM {
    long number;
    SIM(long number){
        this.number = number;
    }
    long getNumber(){
        return number;
    }
}
public class MobileTelephone {
    SIM sim;
    void setSIM(SIM card){
        sim = card;
    }
    long lookNumber(){
        return sim.getNumber();
    }
}
    public static void main(String[] args) {
        SIM simOne = new SIM(13889776509L);
        MobileTelephone mobile = new MobileTelephone();
        mobile.setSIM(simOne);
        System.out.println("手机号码:"+mobile.lookNumber());
        SIM simTwo = new SIM(15967563567L);
        mobile.setSIM(simTwo);
        System.out.println("手机号码:"+mobile.lookNumber());
    }
9、计算圆、梯形的面积
public class Tixing {
    double above,bottom,height;
    Tixing(double a,double b,double h){
        above = a;
        bottom = b;
        height = h;
    }
    double getArea(){
        return (above+bottom)*height/2;
    }
}
public class Student {
    double computerArea(Circle c){
        double area = c.getArea();
        return area;
    }
    double computerArea(Tixing t){
        double area = t.getArea();
        return area;
    }
}
public class Circle {
    double radius,area;
    void setRadius(double r) {
    radius = r;
}
 double getArea() {
     area = 3.14*radius*radius;
     return area;
 }   
}
    public static void main(String[] args) {
        Circle circle = new Circle();
        circle.setRadius(196.87);
        Tixing lader = new Tixing(3,21,9);
        Student zhang =new Student();
        System.out.println("zhang计算圆的面积：");
        double result = zhang.computerArea(circle);
        System.out.println(result);
        System.out.println("zhang计算梯形的面积：");
        result = zhang.computerArea(lader);
        System.out.println(result);
    }
10、计算评分数
public class Line {
        InputScore one;
        DelScore two;
        ComputerAver three;
        Line() {
            three = new ComputerAver();
            two = new DelScore(three);
            one = new InputScore(two);
            
        } 
        public void givePersonScore(){
            one.inputScore();
        }
}
public class InputScore {
    DelScore del;
    InputScore(DelScore del) {
        this.del = del;
    }
    public void inputScore() {
        System.out.println("请输入评委数");
        Scanner read = new Scanner(System.in);
        int count = read.nextInt();
        System.out.println("请输入各个评委的分数");
        double []a = new double[count];
        for(int i = 0; i < count ;i++){
            a[i] = read.nextDouble();
        }
        del.doDelete(a);
    }
}
public class DelScore {
    ComputerAver computer;
    DelScore(ComputerAver computer){
        this.computer = computer;
    }
    public void doDelete(double[] a){
    java.util.Arrays.sort(a);
    System.out.print("去掉一个最高分："+a[a.length - 1]+",");
    System.out.print("去掉一个最低分："+a[0]+"。");
    double b[] = new double[a.length - 2];
    for(int i = 1 ; i < a.length - 1 ; i++){
    b[i - 1] = a[i];
}
 computer.giveAver(b);   
    }
}
public class ComputerAver {
    public void giveAver(double [] b){
        double sum = 0;
        for(int i = 0 ;i < b.length ;i++){
            sum = sum + b [i];
        }
        double aver = sum/b.length;
        System.out.println("选手最后得分"+aver);
    }
}
    public static void main(String[] args) {
        Line line = new Line();
       line.givePersonScore();
    }
