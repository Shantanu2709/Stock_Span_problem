# Stock_Span_problem
Stock_Span_problem using Stack in Linear time complexity O(n)
//# code
import java.util.*;
class HelloWorld {
    
    public static void Stock_Span(int stock[] , int span[])
    {
        Stack<Integer> s = new Stack<>();
        span[0]=1;
        s.push(0);
        for(int i=1; i<stock.length; i++)
        {
            int currPrice=stock[i];
            while(!s.isEmpty() && currPrice>stock[s.peek()])
            {
                s.pop();
            }
            if(s.isEmpty())
            {
                span[i]=i+1;
            }
            else
            {
                int prev = s.peek();
                span[i]=i-prev;
            }
            s.push(i);
        }
        
        
        
    }
    public static void main(String[] args) 
    {
        int stock[]={100,80,60,70,60,85,100};
        int span[]=new int[stock.length];
        Stock_Span(stock,span);
        for(int i=0; i<span.length; i++)
        {
            System.out.print(span[i]+" ");
        }
       
    }
}
