# homework
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

10、计算评分
public class SingGame {
    public static void main(String[] args) {
        Line line = new Line();
       line.givePersonScore();
    }   
}
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
11、子类的继承性
public class UniverStudent extends Student{
    int multi(int x,int y){
        return x*y;
    }
}
public class Student extends People {
    int number;
    void tellNumber(){
        System.out.printf("学号：%d\t",number);
    }
    int add(int x, int y){
        return x+y;
    }
}
public class People {
    int age ,leg = 2,hand =2;
    protected void showPeopleMess(){
        System.out.printf("%d岁,%d只脚，%d只手", age,leg,hand);
    }
}
    public static void main(String[] args) {
        Student zhang = new Student();
        zhang.age = 17;
        zhang.number = 100101;
        zhang.showPeopleMess();
        zhang.tellNumber();
        int x=9,y=29;
        System.out.print("会做加法");
        int result = zhang.add(x, y);
        System.out.printf("%d+%d=%d\n",x,y,result);
        UniverStudent geng = new UniverStudent();
        geng.age = 21;
        geng.number = 6609;
        geng.showPeopleMess();
        geng.tellNumber();
        System.out.print("会做加法:");
        result = geng.add(x, y);
        System.out.printf("%d+%d=%d\n", x,y,result);
        System.out.print("会做乘法:");
        result = geng.multi(x, y);
         System.out.printf("%d*%d=%d\n",x,y,result);
    }
12、子类继承父类
class People{
    private int averHeight = 166;
    public int getAverHeight(){
        return averHeight;
    }
}
class ChinaPeople extends People{
    int height;
    public void setHeight(int h){
        height = h;
    }
    public int getHeight(){
        return height;
    }
}
    public static void main(String[] args) {
        ChinaPeople zhangSan = new ChinaPeople();
        System.out.println("子类对象未继承的averageHeight的值是："+zhangSan.getAverHeight());
        zhangSan.setHeight(178);
        System.out.println("子类对象的实例变量height的值是："+zhangSan.getHeight());
    }
13、计算优惠价格
public class Goods {
    public double weight;
    public void oldSetWeight(double w){
        weight = w;
        System.out.println("double型的weight="+weight);
    }
    public double oldGetPrice(){
        double price = weight*10;
        return price;
    }  
}
public class CheapGoods extends Goods{
    public int weight ;
    public void newSetWeight(int w){
        weight = w;
        System.out.println("int型的weight="+weight);
    }
    public double newGetPrice(){
        double price = weight*10;
        return price;
    }
}
    public static void main(String[] args) {
        CheapGoods cheapGoods = new CheapGoods();
        cheapGoods.newSetWeight(198);
        System.out.println("对象cheapGoods的weight的值是:"+cheapGoods.weight);
        System.out.println("cheapGoods用子类新增的优惠方法计算价格："+cheapGoods.newGetPrice());
        cheapGoods.oldSetWeight(198.987);
        System.out.println("cheapGoods使用继承的方法（无优惠）计算价格："+cheapGoods.oldGetPrice());
    }
14、类人猿
class 类人猿 {
    void crySpeak(String s) {
        System.out.println(s);
    }
}
class People extends 类人猿 {
    void computer(int a,int b) {
        int c=a*b;
        System.out.println(c);
    }
     void crySpeak(String s) {
        System.out.println("***"+s+"***");
    }
}
    public static void main(String[] args) {
        类人猿 monkey;
        People geng = new People();
        monkey = geng;//monkey是People对象geng的上转型对象
        monkey.crySpeak("I love this game");
    //等同于geng.crySpeak("I love this game");
        People people=(People)monkey;//把上转型对象强制转化为子类的对象
        people.computer(10,10);
    }
15、水煮鱼
abstract class GirlFriend {
    abstract void speak();
    abstract void cooking();
}
class ChinaGirlFriend extends GirlFriend{
    void speak(){
        System.out.println("你好");
    }
    void cooking(){
        System.out.println("水煮鱼");
    }
}
class AmericanGirlFriend extends GirlFriend {
    void speak(){
        System.out.println("hello");
    }
    void cooking(){
        System.out.println("roast beef");
    }
}
 class Boy{
     GirlFriend friend;
     void setGirlfriend(GirlFriend f) {
         friend = f;
     }
     void showGirlFriend(){
         friend.speak();
         friend.cooking();
     }
 }
    public static void main(String[] args) {
       GirlFriend girl = new ChinaGirlFriend();
       Boy boy = new Boy();
       boy.setGirlfriend(girl);
       boy.showGirlFriend();
       girl = new AmericanGirlFriend();
       boy.setGirlfriend(girl);
       boy.showGirlFriend();
    }
16、收费计算
abstract class MotorVehicles{
    abstract void brake();
}
interface MoneyFare{
    void charge();
}
interface ControlTemperature{
    void controlAirTemperature();
}
 class Bus extends MotorVehicles implements MoneyFare{
    void brake(){
        System.out.println("公共汽车使用古毂式刹车技术");
    }
    public void charge(){
        System.out.println("公共汽车：一元/张，不计算公里数");
    }
}
class Taxi extends MotorVehicles implements MoneyFare, ControlTemperature{
    void brake(){
        System.out.println("出租车使用盘式刹车技术");
    }
    public void charge(){
        System.out.println("出租车：2元/公里，起价3公里");
    }
    public void controlAirTemperature(){
        System.out.println("出租车安装了Hair空调");
    }
}
 class Cinema implements MoneyFare ,ControlTemperature {
     public void charge(){
         System.out.println("电影院：门票，十元/张");
     }
     public void controlAirTemperature(){
         System.out.println("电影院安装了中央空调");
     }
 }       
    public static void main(String[] args) {
        // TODO code application logic here
        Bus bus101 = new Bus();
        Taxi buleTaxi = new Taxi();
        Cinema redStarCinema = new Cinema();
        MoneyFare fare;
        ControlTemperature temperature;
        fare = bus101;
        bus101.brake();
        fare.charge();
        fare = buleTaxi;
        temperature = buleTaxi;
        buleTaxi.brake();
        fare.charge();
        temperature.controlAirTemperature();
        fare = redStarCinema;
        temperature = redStarCinema;
        fare.charge();
        temperature.controlAirTemperature();
    }
17、问候习惯
interface SpeakHello{
    void speakHello();
}
class Chinese implements SpeakHello{
    public void speakHello(){
        System.out.println("中国人习惯问候语：你好，你吃饭了吗？");
    }
}
class English implements SpeakHello{
     public void speakHello(){
        System.out.println("英国人习惯问候语：你好，天气不错");
    }
}
class KindHello{
    public void lookHello(SpeakHello hello){
        hello.speakHello();
    }
}
    public static void main(String[] args) {
        KindHello kindHello = new KindHello();
        kindHello.lookHello(new Chinese());
        kindHello.lookHello(new English());
    }
18、广告
public interface Advertisement {
    public void showAdvertisement();
    public String getCorpName();
}
public class AdvertisementBoard {
    public void show(Advertisement adver){
        System.out.println(adver.getCorpName()+"的广告词如下:");
        adver.showAdvertisement();
    }
}
public class BlackLandCorp implements Advertisement {

     public void showAdvertisement(){
         System.out.println("***************");
         System.out.printf("劳动是爹\n土地是妈\n");
         System.out.println("***************");
     }
     public String getCorpName(){
         return "黑土集团";
     }
}
public class WhiteCloudCorp implements Advertisement {
    public void showAdvertisement(){
        System.out.println("@@@@@@@@@@@@@@@@@@@@@@");
        System.out.println("飞机中的战斗机，哎yes！/n");
        System.out.println("@@@@@@@@@@@@@@@@@@@@@@");
    }
    public String getCorpName(){
        return "白云有限公司" ;
    }
}
    public static void main(String[] args) {
        AdvertisementBoard board= new AdvertisementBoard();
        board.show(new BlackLandCorp());
        board.show(new WhiteCloudCorp());
    }
19、红牛农场
public class RedCowForm {
     static String formName;
    RedCow cow;
    RedCowForm(){
    }
    RedCowForm(String s){
        cow = new RedCow(150,112,5000);
        formName = s;
    }
    public void showCowMess(){
        cow.speak();
    }
    class RedCow{
        String cowName = "红牛";
        int height,weight,price;
        RedCow(int h, int w ,int p){
            height =h;
            weight = w;
            price = p;
        }
        void speak(){
            System.out.println("偶是"+cowName+",身高:"+height+"cm 体重:"+weight+"kg,生活在"+formName);
        }
    }
}
    public static void main(String[] args) {
        RedCowForm form = new RedCowForm("红牛农场");
        form.showCowMess();
        form.cow.speak();
    }
20、打印希腊字母表
abstract class OutputAlphabet {
    public abstract void output();
}
public class OutputEnglish extends OutputAlphabet {
    public void output(){
        for(char c ='a';c<='z';c++){
            System.out.printf("%3c",c);
        }
    }
}
public class ShowBoard {
    void showMess(OutputAlphabet show){
        show.output();
    }
}
    public static void main(String[] args) {
        ShowBoard board = new ShowBoard();
        board.showMess(new OutputEnglish());
        System.out.println();
        board.showMess(new OutputAlphabet()
        {   public void output()
        {    for(char c = 'α';c<='ω';c++)
               System.out.printf("%3c",c);
        }
    }
        );
    }
21、欢迎光临
interface SpeakHello{
    void speak();
}
class HelloMachine{
    public void turnOn(SpeakHello hello){
        hello.speak();
    }
}
    public static void main(String[] args) {
        HelloMachine machine = new HelloMachine();
        machine.turnOn( new SpeakHello(){
            public void speak () {
                System.out.println("hello,you are welcome!");
            }
        }
        );
        machine.turnOn( new SpeakHello(){
            public void speak(){
                System.out.println("你好，欢迎光临！");
            }
        }
        );
    }
22、银行收益
public class Bank {
    private int money;
    public void income(int in,int out)throws BankException{
        if(in<=0||out>=0||in+out<=0) {
            throw new BankException(in,out);
        }
        int netIncome = in+out;
        System.out.printf("本次计算出的纯收入是：%d元\n",netIncome);
        money = money + netIncome;
    }
    public int getMoney(){
        return money;
    }
}
public class BankException extends Exception {
    String message;
    public BankException(int m,int n){
        message = "入账资金"+m+"是负数或支出"+n+"是正数，不符合系统要求.";
    }
    public String warnMess(){
        return message;
    }
}
    public static void main(String[] args) {
        Bank bank = new Bank ();
        try{ bank.income(200, -100);
             bank.income(300, -100);
             bank.income(400, -100);
             System.out.printf("银行目前有%d元\n",bank.getMoney());
             bank.income(200, 100);
             bank.income(99999, -100);
        }
        catch(BankException e){
            System.out.println("计算收益的过程出现如下问题：");
            System.out.println(e.warnMess());
        }
        System.out.printf("银行目前有%d元\n",bank.getMoney());
    }
