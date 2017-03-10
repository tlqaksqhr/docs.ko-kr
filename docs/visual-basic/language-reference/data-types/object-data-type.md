---
title: "Object Data Type | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Object"
  - "vb.Variant"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "object variables, Object type"
  - "data types [Visual Basic], assigning"
  - "Object data type"
  - "Object data type, reference"
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Object Data Type
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

개체를 참조하는 주소를 저장합니다.  모든 참조 형식\(문자열, 배열, 클래스 또는 인터페이스\)을 `Object` 변수에 할당할 수 있습니다.  `Object` 변수가 임의의 값 형식\(숫자, `Boolean`, `Char`, `Date`, 구조체 또는 열거형\)을 갖는 데이터를 참조할 수도 있습니다.  
  
## 설명  
 `Object` 데이터 형식은 응용 프로그램에서 인식하는 개체 인스턴스를 포함하여 모든 데이터 형식의 데이터를 가리킬 수 있습니다.  컴파일 타임에 변수가 가리키는 데이터 형식에 대해 모르는 경우 `Object`를 사용합니다.  
  
 `Object`의 기본값은 `Nothing`\(null 참조\)입니다.  
  
## 데이터 형식  
 모든 데이터 형식의 변수, 상수 또는 식을 `Object` 변수에 할당할 수 있습니다.  `Object` 변수가 현재 참조하는 데이터 형식을 확인하려면 <xref:System.Type?displayProperty=fullName> 클래스의 <xref:System.Type.GetTypeCode%2A> 메서드를 사용합니다.  다음은 이에 대한 예입니다.  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 `Object` 데이터 형식은 참조 형식입니다.  그러나 Visual Basic에서는 값 형식의 데이터를 참조하는 `Object` 변수는 값 형식으로 처리합니다.  
  
## 저장소  
 `Object` 변수는 참조하는 데이터 형식에 관계없이 값 자체가 아니라 값에 대한 포인터를 포함합니다.  이 변수는 항상 컴퓨터 메모리에서 4바이트를 사용하지만 변수의 값을 나타내는 데이터를 저장하지는 않습니다.  포인터를 사용하여 데이터를 찾는 코드 때문에 값 형식을 가지고 있는 `Object` 변수는 명시적으로 형식이 지정된 변수에 액세스할 때 보다 다소 느립니다.  
  
## 프로그래밍 팁  
  
-   **Interop 고려 사항.** Automation 또는 COM 개체와 같이 .NET Framework용으로 작성되지 않은 구성 요소를 사용하는 경우 다른 환경에서는 포인터 형식이 Visual Basic `Object` 형식과 호환되지 않는다는 것을 염두에 두고 있어야 합니다.  
  
-   **성능.** `Object` 형식으로 선언된 변수는 어떠한 개체라도 참조할 수 있습니다.  이런 변수에 대한 메서드나 속성을 호출하면 항상 *런타임에 바인딩*됩니다.  성능 향상을 위해 컴파일 타임에 *초기 바인딩*되도록 하려면 변수를 특정 클래스 이름으로 선언하거나 특정 데이터 형식에 캐스팅합니다.  
  
     개체 변수를 선언하는 경우 일반화된 `Object` 형식 대신 <xref:System.OperatingSystem>과 같은 특정 클래스 형식을 사용하십시오.  <xref:System.Windows.Forms.Control> 대신 <xref:System.Windows.Forms.TextBox>처럼 가장 구체적인 클래스를 사용하여 속성과 메서드에 액세스할 수 있습니다.  대개 **Object Browser**의 **Classes** 목록을 사용하여 사용 가능한 클래스 이름을 찾을 수 있습니다.  
  
-   **확대 변환.** 모든 데이터 형식과 모든 참조 형식은 `Object` 데이터 형식으로 확대 변환됩니다.  이것은 <xref:System.OverflowException?displayProperty=fullName> 오류의 발생 없이 형식을 `Object`로 변환할 수 있음을 의미합니다.  
  
     값 형식과 `Object` 간을 변환하는 경우 Visual Basic에서는 *boxing* 및 *unboxing*이라는 작업을 수행하므로 실행 시간이 오래 걸립니다.  
  
-   **형식 문자.** `Object`에는 리터럴 형식 문자나 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Object?displayProperty=fullName> 클래스입니다.  
  
## 예제  
 다음 예제에서는 개체 인스턴스를 가리키는 `Object` 변수를 보여 줍니다.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## 참고 항목  
 <xref:System.Object>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [How to: Determine Whether Two Objects Are Related](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [How to: Determine Whether Two Objects Are Identical](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)