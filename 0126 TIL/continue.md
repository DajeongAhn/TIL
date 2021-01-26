# 반복문

### - 반복제어

`break`, `continue`, `for-else`

1. break : while문, for문 등 반복문에서 멈추게 하는 제어문

2. continue : continue 이후의 코드를 수행하지 않고 *다음 요소부터*  계속하여 반복을 수행

   ```python
   def lonely(num_list):
       result = []
       for num in num_list:
           if result[-1:] == [num]: continue
           result.append(num)
           
       return result
       
   print(lonely([1, 1, 3, 3, 0, 1, 1])) => [1, 3, 0, 1]
   print(lonely([4, 4, 4, 3, 3])) => [4, 3]
   ```

   > => 오늘 0126 workshop 3번 문제 풀면서 continue의 쓰임 재발견!!

3. else : 끝까지 반복문을 실행한 이후에 실행

   - 반복에서 리스트의 소진이나 (`for` 의 경우) 조건이 거짓이 되어 (`while` 의 경우) 종료할 때 실행
   - 그러나, 반복문이 `break` 문으로 종료될 때는 실행X (즉, `break`를 통해 중간에 종료되지 않은 경우만 실행)

4. pass : 아무것도 하지 않는다.

   => 문법적으로 문장이 필요하지만, 프로그램이 특별히 할 일이 없을 때 자리 채우는 용도로 사용

5. pass VS continue 

   => pass는 에러의 발생을 막고 자리를 비워두기 위해 사용(반복제어는 아님)

   ​      continue 이후의 코드를 수행하지 않고 다음 요소로 넘어가서 반복 수행하  도록 하는 것

