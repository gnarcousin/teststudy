<h2>대선</h2>

대선 1(투표 입력 기능)
```java
package march;
import java.util.Scanner;

public class vote_counter_1_3 {
	//표수, 동률 뽑아오는 최종버전
	static String[][] dn = {{" 이재명","0"},{" 윤석열","0"},{" 심상정","0"},{" 안철수","0"},{,}};//2차원배열에 후보 이름과 표를 저장(string으로 저장됨)
	String duece = "";//후보(들)가 들어가는 부분
	
	String vote_cheker(int vote_can)
	{
		int top = Integer.parseInt(dn[0][1]);//비교대상을 후보 1 기준으로 설정
		//각 후보 득표수 더하기
		if(vote_can == 1)
		{
			dn[0][1] = Integer.toString(Integer.parseInt(dn[0][1])+1);
		}
		else if(vote_can == 2)
		{
			dn[1][1] = Integer.toString(Integer.parseInt(dn[1][1])+1);
		}
		else if(vote_can == 3)
		{
			dn[2][1] = Integer.toString(Integer.parseInt(dn[2][1])+1);
		}
		else if(vote_can == 4)
		{
			dn[3][1] = Integer.toString(Integer.parseInt(dn[3][1])+1);
		}else
		{
		}
		//후보들 비교해서 1등 뽑기 (후보 2명까지)
		for (int i=0; i< dn.length-1; i++) //배열 길이만큼 반복
		{
	         if (top<Integer.valueOf(dn[i][1]))//각 후보와 1번후보를 비교
	         {
	            top = Integer.valueOf(dn[i][1]);//top에 가장 득표가 많은 후보 넣기
	         }
	    }
		duece = "";//후보 들어가는 부분 초기화
		for (int i=0; i < dn.length-1; i++) //배열 길이만큼 반복
		{
	         if (top == Integer.valueOf(dn[i][1])) //가장득표가 많은 후보와 다른후보가 같다면
	         {
	        	 duece += dn[i][0];//듀스에 표가 같은 후보 2명이상 반환
	         }
        }	
		return duece;//듀스값 반환
	}
	public static void main(String[] args) {
		int vote_can = 0;//사용자 투표 번호
		String vote_chk;//투표 할지 안할지
	
		Scanner sc = new Scanner(System.in);//문자
		Scanner sd = new Scanner(System.in);//정수
		
		vote_counter_1_3 vc = new vote_counter_1_3();
	
		System.out.println("[2022 대선 투표 프로그램]");
		System.out.println();
    
		while(true)
		{
			
			System.out.printf("안녕하세요. 투표하시겠습니까? (y/n) ");
			vote_chk = sc.nextLine();
			if(vote_chk.equals("y"))
			{
				System.out.println();
				System.out.println("1.이재명 2.윤석열 3.심상정 4.안철수");
				System.out.printf("투표하실 후보를 선택해주세요 : ");
				vote_can = sd.nextInt();//1,2,3,4 중에 한값 받음
				
				vc.vote_cheker(vote_can);//위에 선언한 함수 사용
				
				System.out.println();
				System.out.printf("현재 1등후보는%s 입니다\n", vc.duece);
				System.out.printf("이재명 [%s]표 || 윤석열 [%s]표 || 심상정 [%s]표 || 안철수 [%s]표\n",dn[0][1],dn[1][1],dn[2][1],dn[3][1]);
				System.out.println();
			}
			else
			{
				break;
			}
			
        }
		System.out.printf("최종 당선인은%s 입니다.\n",vc.duece);
		System.out.println("안녕히가십쇼.");
```
대선 2(랜덤 선출 기능)

```java
import java.util.Random;


public class Project06 {
    // 총 투표수 10,000건
    static int totalCnt = 10000;

    public static void main(String[] args) {
        Random random = new Random();
        int[] candidate = new int[4];
        String[] name = new String[]{"이재명", "윤석열", "심상정", "안철수"};
        // 각 투표수의 결과는 동일한 비율로 랜덤하게 발생
        for (int i = 1; i <= totalCnt; i++) {
            // 나눈값이 : 0 1 2 3 이 나오면 1:1:1:1 이다. 25%확률
            int voteRate = (random.nextInt(4) + 1) % 4;
            candidate[voteRate]++;
            System.out.println();
            System.out.printf("[투표진행율]: %05.02f%c, %d명 투표 => %s\n", ((double) candidate[voteRate] / (double) totalCnt) * 100.0f, '%', (int) candidate[voteRate], name[voteRate]);
            System.out.printf("[기호:1] 이재명: %05.02f%c, (투표수: %d)\n", ((double) candidate[0] / (double) totalCnt) * 100.0f, '%', candidate[0]);
            System.out.printf("[기호:2] 윤석열: %05.02f%c, (투표수: %d)\n", ((double) candidate[1] / (double) totalCnt) * 100.0f, '%', candidate[1]);
            System.out.printf("[기호:3] 심상정: %05.02f%c, (투표수: %d)\n", ((double) candidate[2] / (double) totalCnt) * 100.0f, '%', candidate[2]);
            System.out.printf("[기호:4] 안철수: %05.02f%c, (투표수: %d)\n", ((double) candidate[3] / (double) totalCnt) * 100.0f, '%', candidate[3]);
            if (i == totalCnt) {
                int max = 0;
                for (int j = 0; j < 4; j++) {
                    if (max < candidate[j]) {
                        max = candidate[j];
                    }
                }
                int same = 0;
                for (int j = 0; j < 4; j++) {
                    if (max == candidate[j]) {
                        same++;
                    }
                }

                if (same > 1) {
                    i--;
                }
            }
        }
        int max = 0;
        String vitorier = new String();
        for (int i = 0; i < 4; i++) {
            if (max < candidate[i]) {
                max = candidate[i];
                vitorier = name[i];
            }
        }
        System.out.printf("[투표결과] 당선인: %s\n", vitorier);
    }
}
```
<h2>달력 만들기</h2>

```java
import java.util.*;
public class 달력만들기{
   public static void main(String[] args){
       
       int year=0, month=0;
       Scanner scan=new Scanner(System.in);
       System.out.println("년도 입력: ");
       year=scan.nextInt();
       
       System.out.println("월 입력: ");
       month=scan.nextInt();
       
       //출력
       String[] strWeek= {"일","월","화","수","목","금","토"};
       System.out.println(year+"년도 "+month+"월");
       
       for(String week:strWeek)
       {
           System.out.print(week+"\t");
       }
       int total=(year-1)*365
                +(year-1)/4
                -(year-1)/100
                +(year-1)/400;
       //전달
       int[] lastDay= {31,28,31,30,31,30,31,31,30,31,30,31};
       if((year%4==0 && year%100!=0)||(year%400==0)) //윤년 => 2월 29일
           lastDay[1]=29;
       else
           lastDay[1]=28;
       for(int i=0;i<month-1;i++)
       {
           total+=lastDay[i];
       }
       //1일자의 요일
       total++;

       int week=total%7;
       //달력 출력
       System.out.println();
       for(int i=1;i<=lastDay[month-1];i++)
       {
           if(i==1)
           {
              for(int j=0;j<week;j++)
              {
               System.out.print("\t");
              }
           }
           System.out.printf("%2d\t",i);
           week++;
           if(week>6)
           {
               week=0;
               System.out.println();
               }
       }
   }
}
```
<h2>구구단</h2>

```java
public class Multiplication {

  public static void main(String[] args) {
    for (int i = 1; i <= 9; i++) {
      for (int j = 2; j <= 9; j++) {
        System.out.print(j + " * " + i + " = " + String.format("%2d", i * j));
        System.out.print("    ");
      }
      System.out.println();
    }
  }
}
```
<h2> 윤년 판단 프로그램 </h2>

```java
import java.util.Scanner;
public class LeapYearCheck01 {
	public static void main(String[] args) {
		System.out.println("연도를 입력하시오.");
		Scanner sc = new Scanner(System.in);
		int year = sc.nextInt();
		if ((year % 4 == 0 && year % 100 != 0) || year % 400 == 0) {
			System.out.println(year + "년은 윤년");
		} else {
			System.out.println(year + "년은 평년");
		}
	}
}
```
GregorianCalender 사용
```java
import java.util.GregorianCalendar;
import java.util.Scanner;
public class LeapYearCheck02 {
	public static void main(String[] args) {
		System.out.println("연도를 입력하시오.");
		Scanner sc = new Scanner(System.in);
		int year = sc.nextInt();

		GregorianCalendar gc = new GregorianCalendar();
		if (gc.isLeapYear(year)) {
			System.out.println(year + "년은 윤년");
		} else {
			System.out.println(year + "년은 평년");
		}
	}
}
```

<h2> 달의 일수 출력 </h2>

```java
public class switchmonthday {
    public static void main(String[] args) {
        System.out.println("일수를 알고싶은 달을 입력하세요 : ");
        Scanner sc=new Scanner(System.in);
        int position=sc.nextInt();

        switch (position) {
            case 1: case 3: case 5: case 7: case 8: case 10: case 12 :
                System.out.println("달의 일수는 : 31입니다.");
                break;
 
            case 4: case 6: case 11: case 9:
                System.out.println("달의 일수는 : 30입니다.");
                break;
 
            case 2:
                System.out.println("달의 일수는 : 28입니다."); 
                break;

            default: 
                System.out.println("달의 일수를 확인하세요."); 
        }
    }
}
```

<h2> 로또 </h2>

```java
package ws;

import java.util.*;

public class Ws02 {
	public static void main(String[] args) {	
		// 당첨번호: 난수로 6개(중복 x)(1~45)
		Random r = new Random();
		int ar[] = new int[6];

		List<Integer> lucky = new ArrayList<>();
		
		for (int i = 0; i < ar.length; i++) {
			ar[i] = r.nextInt(45) + 1;
			for (int j = 0; j < i; j++) {
				int t = ar[j];
				if(ar[i] == ar[j]) {
					i--;
				}
				lucky.add(t);
			}
		}
		System.out.println("당첨번호: " + Arrays.toString(ar));
		System.out.println("------------------");
		
		// 로또 번호 출력: 2x6사이즈, 1~45 (한 행에서 중복되지 않게)
		// 일치하는 수가 3개 이상이면 당첨
		// 3개: 4등 10만원, 4개: 3등 20만원, 5개: 2등 50만원, 6개: 1등 100만원
		
		List<Integer> list = new ArrayList<>();
		List<Integer> list2 = new ArrayList<>();

		int[][] buy = new int[2][6];
		int count = 0;
		
		int first = 1000000;
		int second = 500000;
		int third = 200000;
		int fourth = 100000;
		
		// 마지막에 총 당첨금 나오게 하기
		int total = 0;
		
		for (int i = 0; i < buy.length; i++) {			
			for (int j = 0; j < buy[0].length; j++) {
				int z = buy[i][j];
				buy[i][j] = r.nextInt(45) + 1;
				
				boolean same = list.contains(z);
				boolean same2 = list2.contains(z);
				boolean happy = lucky.contains(z);
				
				
				//1번째, 2번째에서는 중복 가능
				if(i == 0) {
					if(same || z == 0) {
						j--;
						continue;
					}else {
						buy[i][j] = z;
						list.add(z);
						
				} 	if (happy) {
					count++;
				}	if(j == (buy[0].length - 1)) {		
					if(count >= 3) {
						System.out.println("First round: " + Arrays.toString(buy[0]));
						System.out.printf("%d개 일치. 당첨!\n",count);
						switch(count) {
						case 3:
							System.out.printf("4등. %d원\n",fourth);
							total += fourth;
							break;
						case 4:
							System.out.printf("3등. %d원\n",third);
							total += third;
							break;
						case 5:
							System.out.printf("2등. %d원\n",second);
							total += second;
							break;
						case 6:
							System.out.printf("1등. %d원\n",first);
							total += first;
							break;
						}
						System.out.println("");
						count = 0;	
						continue;
					}else
					{System.out.println("First round: " + Arrays.toString(buy[0]));
						System.out.printf("%d개 일치. 다음 기회에...\n",count);
						System.out.println("");

						count = 0;
						continue;
					}
					} 							
				}else {
					if(same2 || z == 0) {
						j--;
						continue;
					}else {
						buy[i][j] = z;
						list2.add(z);
				}
					if (happy) {
						count++;
					}	if(j == (buy[0].length - 1)) {
						if(count >= 3) {
							System.out.println("Second round " + Arrays.toString(buy[1]));
							System.out.printf("%d개 일치. 당첨!\n",count);
							switch(count) {
							case 3:
								System.out.printf("4등. %d원\n",fourth);
								total += fourth;
								break;
							case 4:
								System.out.printf("3등. %d원\n",third);
								total += third;
								break;
							case 5:
								System.out.printf("2등. %d원\n",second);
								total += second;
								break;
							case 6:
								System.out.printf("1등. %d원\n",first);
								total += first;
								break;
							}
						}
						else{
							System.out.println("Second round " + Arrays.toString(buy[1]));
							System.out.printf("%d개 일치. 다음 기회에...\n",count);
						}
					}
				}
				}
					}
		System.out.println("");
		System.out.println("Total " + total + "원");
				}
	}
```
로또 번호 생성
```java
import java.io.IOException;
import java.util.Arrays;

public class Exm {
	public static void main(String[] args) throws IOException {
		System.out.println("＊로또번호 랜덤 생성＊"); 
		int idx_num = 0;
		int lotto_num[] = new int[6]; 
		
		String result_txt = "";
		
		for(int i=1; i<=30; i++){ 
			
			result_txt = "";
			result_txt += idx_num+1+"회 : [ "; 
			
			//6개의 랜덤번호를 저장
			for(int j=0; j<=5; j++){
				int num_temp = (int) (Math.random()*44+1);
				lotto_num[j] = num_temp; 
			} 
			//저장된 숫자 정렬
			Arrays.sort(lotto_num); 
			
			//중복된 값 체크
			boolean duple = false;
			for(int k=0; k<lotto_num.length; k++){ 
				if(k==lotto_num.length-1) { //6번째 숫자일 경우 
					result_txt += lotto_num[k]+" ]"; 	
				}else if(lotto_num[k]!=lotto_num[k+1]){ //list 내 인접한 숫자가 중복되지 않을 경우
					result_txt += lotto_num[k]+", \t"; 
				}else { //중복된 숫자가 있을 경우 flag 체크
					duple = true;
				}
			}
			if(idx_num==5)break; //로또번호는 5번만 출력
			if(duple==false) { //중복된 숫자가 없으면 로또번호 출력
				idx_num++;
				System.out.println(result_txt);	
			}
		}
	}
}
```