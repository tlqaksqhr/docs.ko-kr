---
title: "stackalloc(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "stackalloc_CSharpKeyword"
  - "stackalloc"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "stackalloc 키워드[C#]"
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# stackalloc(C# 참조)
`stackalloc` 키워드는 안전하지 않은 코드 컨텍스트에서 스택에 메모리 블록을 할당하는 데 사용됩니다.  
  
```  
int* block = stackalloc int[100];  
```  
  
## 설명  
 키워드는 지역 변수 이니셜라이저에서만 유효합니다.  다음 코드는 컴파일러 오류를 발생시킵니다.  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 포인터 형식이 관련되기 때문에 `stackalloc`에는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 컨텍스트가 필요합니다.  자세한 내용은 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)를 참조하십시오.  
  
 `stackalloc`는 C 런타임 라이브러리의 [\_alloca](/visual-cpp/c-runtime-library/reference/alloca)와 비슷합니다.  
  
 다음 예제는 피보나치 수열의 20번째 숫자까지 계산 및 표시합니다.  각 번호에는 이전 두 숫자의 합계입니다.  이 코드에서 `int` 형식의 요소 100개를 포함하는 데 충분한 크기의 메모리 블록은 힙이 아니라 스택에 할당됩니다.  블록의 주소는 포인터 `fib`에 저장됩니다.  이 메모리는 가비지 수집의 영향을 받지 않으므로 [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)를 사용하여 고정하지 않아도 됩니다.  메모리 블록의 수명은 해당 메모리 블록이 정의된 메서드의 수명에 따라 제한됩니다.  즉, 메서드에서 반환하기 전에는 메모리를 해제할 수 없습니다.  
  
## 예제  
 [!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## 보안  
 안전하지 않은 코드는 안전한 코드보다 위험합니다.  그러나 `stackalloc`을 사용하면 CLR\(공용 언어 런타임\)에서 버퍼 오버런 감지 기능이 자동으로 활성화됩니다.  버퍼 오버런을 감지하면 프로세스가 가능한 한 신속하게 종료되어 악의적인 코드가 실행될 가능성을 최소화합니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)