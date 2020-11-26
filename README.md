# java

package com.bkh37.array;

import java.util.Arrays;

//배열 복사
//능력단위 : 프로그래밍 언어활용
//능력단위요소 : 기본문법 활용하기
//2020-11-26

/* 배열복사
 * 
 * 얉은 복사 shallow copy
 * 			배열 객체를 복사하는 것이 아니라 배열의 ref만 복제
 * 
 * 깊은 복사 deep copy
 * 			배열을 통째로 복사하여 새로운 배열을 생성후
 * 			그 ref를 리턴합니다.
 * 			대표 API로 System.arrayCopy();가 있습니다.
 *	
 * 
 * 
 */

public class ArrayCopy01 {
	public static void main(String[] args) {
		
		int[] arr01 = new int[] {10,20,30,40,50};
		
		int[] arr02 = arr01;
		
		arr01[0] = 111;
		arr02[1] = 55; 
		
		System.out.println(Arrays.toString(arr01));
		System.out.println(Arrays.toString(arr02));
		System.out.println();
		
		//깊은 복사 = 배열을 통째로 복사한 후 복사본을 넘겨준다.
		//원본 보존
		
		int[] arr03 = new int[arr01.length];
		for(int i = 0; i < arr03.length; i++) {
			arr03[i] = arr01[i];
		}
		
		arr01[0] = 100;
		arr03[arr03.length - 1] = 555; 
		
		System.out.println("1 " + Arrays.toString(arr01));
		System.out.println("2 " + Arrays.toString(arr02));
		System.out.println("3 " + Arrays.toString(arr03));
		System.out.println();System.out.println();
		//API이용해서 하기
		//System.arrayCopy();
		
		int[] arr04 = new int[arr01.length];
		
		
		System.arraycopy(arr01, 0, arr04, 0, arr01.length);
		
		arr01[0] = 15;
		arr04[2] = 15;
		
		System.out.println("1 " + Arrays.toString(arr01));
		System.out.println("4 " + Arrays.toString(arr04));
		
		
		int[] arr05 = null;
		//객체 null
		System.out.println(arr05);
		
		arr05 = new int[10];
		System.out.println(Arrays.toString(arr05));

	}
}

