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
    
