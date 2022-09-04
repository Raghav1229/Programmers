## :round_pushpin: 해시 - 전화번호 목록

***

<br>

### :pushpin: 통과한 코드

```java
import java.util.*;

class Solution {
    public boolean solution(String[] phone_book) {
        boolean answer = true;
        
        Arrays.sort(phone_book);
        int size = phone_book.length-1;
        
        for(int idx=0; idx < size; idx++){
            if(phone_book[idx+1].indexOf(phone_book[idx]) == 0) return false; 
        }
        
        return answer;
    }
}
```

<br>



### :pushpin: 효율성 탈락한 코드

```java
import java.util.*;

class Solution {
    public boolean solution(String[] phone_book) {
        boolean answer = true;

        HashSet<String> phone_set = new HashSet<String>(Arrays.asList(phone_book));
        String next_elem;
        String nextnext;
        
        List<String> list = new ArrayList<String>(Arrays.asList(phone_book));
        Iterator<String> iter = phone_set.iterator();
        Iterator<String> iter2 = list.iterator();
        
        while(iter.hasNext()){
            next_elem = iter.next();
            
            while(iter2.hasNext()){
                nextnext = iter2.next();
                if(!next_elem.equals(nextnext) && next_elem.indexOf(nextnext) == 0){
                    return false;
                }
            }
            iter2 = list.iterator();
        }
        
        
        return answer;
    }
}
```

