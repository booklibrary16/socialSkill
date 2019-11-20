
public class OulerProject {
       public static void main(String[] args)
       {
           int index;
           long[] index15 = new long[]{1l,0l,0l,0l,0l,0l,0l,0l,0l,0l,0l,0l,0l,0l,0l,0l,0l,0l,0l,0l};
           long cut;

           cut = 1000000000000000l;
           String str = "";
           index = 20;
           long out = 1;
           for(int i = 0;i<1000;i++)
           {
               for(int j=0;j<index;j++)
                   index15[j] *= 2l;

               for(int j=0;j<index-1;j++)
               {
                   index15[j+1] += index15[j]/cut;
                   index15[j] = index15[j]%cut;
               }
               System.out.println(i);
           }
           for(int j=0;j<index;j++)
               str += ""+ index15[index-1-j];

           char c[] = str.toCharArray();
           int num=0;
           for(int ii=0;ii<str.length();ii++)
               num += c[ii]-'0';
           System.out.println(num);

       }
}
