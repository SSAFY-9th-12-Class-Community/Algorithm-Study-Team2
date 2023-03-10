문제 회고를 위해 알고리즘 풀이 기록을 남깁니다.

# 백준 문제번호 문제제목
[1978 소수 찾기](https://www.acmicpc.net/problem/1978)

### 문제 이해하기
주어진 수 N개 중에서 소수가 몇개인지 찾아서 출력하는 프로그램
 

### 문제 접근 방법
1. 시간 제한은 2초, N의 범위가 100이하이고, 1000이하의 자연수만 주어진다.
2. 시간적으로 여유가 있기 때문에 들어오는 숫자 하나하나 소수인지 판별하였다.
3. 소수를 판별하기 위해 2 ~ 루트(N)의 수로 나누어 떨어지는지 체크하였다.
4. 나누어 떨어지면 소수가 아닌걸로 판단하였다.

### 구현 배경 지식
1. 소수에 대한 이해
2. 소수 찾기 최적화에 대한 이해

### 접근 방법을 적용한 코드
```java
import java.util.Scanner;

public class bj_1978_lyj {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        int count = 0;
        for (int i = 0; i < N; i++) {
            if (isPrime(sc.nextInt()))
                count++;
        }
        System.out.println(count);
    }

    static boolean isPrime(int n) {
        if (n == 1)
            return false;
        if (n == 2)
            return true;

        for (int i = 2; i < (int)Math.sqrt(n) + 1; i++) {
            if (n % i == 0)
                return false;
        }
        return true;
    }
}
```

