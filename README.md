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
2、遍历数组
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
