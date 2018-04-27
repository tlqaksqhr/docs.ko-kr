---
title: 배열 문제 해결(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e5c00c2b531dd019a207b16ffcac95424bfe450
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="troubleshooting-arrays-visual-basic"></a>배열 문제 해결(Visual Basic)
이 페이지는 배열에서 작업할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열 합니다.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>컴파일 오류를 선언 하 고 배열을 초기화 하는 중  
 선언 만들고 배열 초기화에 대 한 규칙의 잘못 이해에서 컴파일 오류가 발생할 수 있습니다. 오류의 가장 일반적인 원인은 다음과 같습니다.  
  
-   제공 된 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 차원 길이 지정 하는 배열 변수 선언 뒤에 절. 다음 코드 줄에는 이러한 종류의 잘못 된 선언을 보여 줍니다.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   가변 배열의 최상위 배열 보다 그 이상 차원 길이 지정 합니다. 다음 코드 줄에는 이러한 종류의 잘못 된 선언을 보여 줍니다.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   생략 된 `New` 요소 값을 지정할 때 키워드입니다. 다음 코드 줄에는 이러한 종류의 잘못 된 선언을 보여 줍니다.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   제공 된 `New` 중괄호 없이 절 (`{}`). 다음 코드 줄에는 이러한 종류의 잘못 된 선언을 보여 줍니다.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>범위를 벗어난 배열 액세스  
 배열을 초기화 하는 프로세스에서 각 차원에 상한값 및 하한값을 할당 합니다. 배열의 요소에 대 한 모든 액세스 유효한 인덱스 또는 모든 차원에 대해 아래 첨자를 지정 해야 합니다. 인덱스 보다 또는 해당 상한을 초과 경우는 <xref:System.IndexOutOfRangeException> 예외가 발생 합니다. 컴파일러 실행 시 오류가 발생 하므로 이러한 오류를 검색할 수 없습니다.  
  
### <a name="determining-bounds"></a>범위 결정  
 다른 구성 요소 코드를 배열에 전달 하는 경우 예를 들어 프로시저 인수로 모르는 해당 배열의 크기 또는 차원의 길이입니다. 요소에 액세스 하기 전에 항상 배열의 모든 차원에 대 한 상한을 결정 해야 합니다. Visual Basic 이외의 방법으로 배열의 만들어졌으면 `New` 절 하한값 0 이외의 있으며 것도 해당 하한값을 확인 하는 것이 가장 안전 합니다.  
  
### <a name="specifying-the-dimension"></a>차원 지정  
 다차원 배열의 범위를 결정할 때는 주의 해야 차원을 지정 하는 방법은 합니다. `dimension` 의 매개 변수는 <xref:System.Array.GetLowerBound%2A> 및 <xref:System.Array.GetUpperBound%2A> 메서드는 0부터 시작 하는 동안는 `Rank` Visual Basic의 매개 변수 <xref:Microsoft.VisualBasic.Information.LBound%2A> 및 <xref:Microsoft.VisualBasic.Information.UBound%2A> 함수는 1부터 시작 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [방법: Visual Basic에서 배열 변수 초기화](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
