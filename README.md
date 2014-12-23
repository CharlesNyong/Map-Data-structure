Map-Data-structure
==================
package Java.com;
import java.util.*;

public class Map<T> {
    
	private ArrayList<T>store;
	private boolean flag;
	
	public Map(){
	 store = new ArrayList<T>();
	 flag = false;
	}
	
	public T get(int key){
	 T m =null;
	 
	   for(int i=0; i<store.size(); i++){
		  
		  if(i == key)
		  {
			m = (store.get(i));
			break;
		  }
	   }
	   
	  return (m); 
	}
	
	public T put(int k, T s){
	T y = null;
	   
	if(flag ==false){
	  	   store.add(k, s);
	  	   flag = true;
		  }
	else{
	  for(int l=0; l<store.size(); l++){
	      
		    
		   if(l== k){
			  
			    y = store.get(l);
			    store.remove(l);
			    store.add(l, s);
			    break;
			   }
		   else if(l!=k){
			store.add(k, s);
			break;   
		   }
	}
}	  
	  
		if(y==null){
		//System.out.println("previous not found new item added");
		return null;
		}
		else{
		return y;	
		}
}
	
 public String toString(T l){
	return(l.toString());	
}	
	
	
	public static void main(String[] args) {
		
	 Client a = new Client("charles", 10395488);
	 Client b = new Client("frank", 103959488);
	 Client c = new Client("Dan", 10395);
	 Client d = new Client("Carl", 10388);
	 Client e = new Client("Tony", 103456);
	 Client f = new Client("henry", 103488);
	
	 Map<Client> t = new Map<Client>();
	
	 System.out.println(" " + t.put(0, a));
	 System.out.println(" " + t.put(0, b));
	 t.put(1, f);
	 t.put(2, e);
	 t.put(2, c);
	 System.out.println("\n");
	 System.out.println("== " + t.get(2));
	 
	 
	 
	}

}
