---
title: "Troubleshooting Arrays (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "troubleshooting arrays"
  - "arrays [Visual Basic], initialization errors"
  - "troubleshooting Visual Basic, arrays"
  - "arrays [Visual Basic], compilation errors"
  - "arrays [Visual Basic], declaration errors"
  - "arrays [Visual Basic], troubleshooting"
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Troubleshooting Arrays (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 페이지에서는 배열 작업 시 발생할 수 있는 몇 가지 일반적인 문제를 나열합니다.  
  
## 배열 선언 및 초기화 시 컴파일 오류  
 배열을 선언, 작성 및 초기화하는 규칙을 잘못 이해하면 컴파일 오류가 발생할 수 있습니다.  이 오류의 가장 일반적인 원인은 다음과 같습니다.  
  
-   배열 변수 선언에서 차원 길이를 지정한 후 [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) 절 입력.  다음 코드 줄에서 이러한 형식의 잘못된 선언을 보여 줍니다.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   가변 배열의 최상위 배열보다 많게 차원 길이 지정.  다음 코드 줄에서 이러한 형식의 잘못된 선언을 보여 줍니다.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   요소 값을 지정할 때 `New` 키워드 생략.  다음 코드 줄에서 이러한 형식의 잘못된 선언을 보여 줍니다.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   중괄호\(`{}`\)를 사용하지 않고 `New` 절 입력.  다음 코드 줄에서 이러한 형식의 잘못된 선언을 보여 줍니다.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## 범위를 벗어난 배열 액세스  
 배열을 초기화하는 과정에서 각 차원에 상한과 하한을 할당합니다.  배열 요소에 액세스하는 모든 경우에 모든 차원에 대해 유효한 인덱스 또는 첨자를 지정해야 합니다.  하한보다 낮거나 상한보다 높은 인덱스가 있는 경우 <xref:System.IndexOutOfRangeException> 예외가 발생합니다.  컴파일러에서 이러한 오류를 감지할 수 없으므로 런타임에 오류가 발생합니다.  
  
### 범위 결정  
 다른 구성 요소가 배열을 프로시저 인수로서 코드에 전달하는 경우에는 배열의 크기나 차원의 길이를 알 수 없습니다.  따라서 요소에 액세스하기 전에 배열의 모든 차원에 대해 상한을 항상 확인해야 합니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] `New` 절 이외의 다른 방법으로 배열을 만든 경우 하한이 0 이외의 값일 수도 있으므로 하한도 확인하는 것이 안전합니다.  
  
### 차원 지정  
 다차원 배열의 범위를 결정할 때 차원을 지정하는 방법에 주의해야 합니다.  <xref:System.Array.GetLowerBound%2A> 및 <xref:System.Array.GetUpperBound%2A> 메서드의 `dimension` 매개 변수는 0부터 시작하지만 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A> 및 <xref:Microsoft.VisualBasic.Information.UBound%2A> 함수의 `Rank` 매개 변수는 1부터 시작합니다.  
  
## 참고 항목  
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)