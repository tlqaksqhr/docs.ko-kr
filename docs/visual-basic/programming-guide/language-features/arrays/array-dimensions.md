---
title: "Array Dimensions in Visual Basic | Microsoft Docs"
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
  - "dimensions, arrays"
  - "arrays [Visual Basic], dimensions"
  - "arrays [Visual Basic], rectangular"
  - "arrays [Visual Basic], rank"
  - "rectangular arrays"
  - "ranking, arrays"
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Array Dimensions in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*차원*은 배열 요소의 사양이 달라질 수 있는 방향입니다.  특정 달의 날짜별 총 판매액이 들어 있는 배열은 해당 달의 날짜에 해당하는 차원을 하나 갖습니다.  특정 달의 부서별 매일 총 판매액이 들어 있는 배열은 부서 번호와 해당 달의 날짜에 해당하는 두 개의 차원을 갖습니다.  배열의 차원 수를 *차수*라고 합니다.  
  
> [!NOTE]
>  <xref:System.Array.Rank%2A> 속성을 사용하여 배열에 있는 차원의 수를 확인할 수 있습니다.  
  
## 차원 사용  
 배열의 각 차원에 대한 *인덱스*나 *첨자*를 지정하여 배열 요소를 지정할 수 있습니다.  요소는 각 차원에서 인덱스 0부터 해당 차원의 가장 높은 인덱스까지 연속되어 있습니다.  
  
 다음 그림에서는 여러 차수의 배열에 대한 개념적 구조를 보여 줍니다.  그림의 각 요소는 해당 요소에 액세스하는 인덱스 값을 보여 줍니다.  예를 들어, 인덱스 `(1, 0)`을 지정하면 2차원 배열의 두 번째 행에 있는 첫 번째 요소에 액세스할 수 있습니다.  
  
 ![1차원 배열의 그래픽 다이어그램](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.png "ArrayExDimOne")  
1차원 배열  
  
 ![2차원 배열의 그래픽 다이어그램](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")  
2차원 배열  
  
 ![3차원 배열의 그래픽 다이어그램](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.png "ArrayExDimThree")  
3차원 배열  
  
### 1차원  
 대부분의 배열은 1차 배열이며, 이러한 배열의 예로는 각 나이에 해당하는 사람 수를 나타내는 배열이 있습니다.  이 경우 요소를 지정하는 데 필요한 유일한 요건은 카운트를 보유하는 대상인 나이입니다.  따라서 이러한 배열에서는 인덱스를 하나만 사용합니다.  다음 예제에서는 나이 0부터 120까지에 대한 나이 카운트가 들어 있는 *1차원 배열*을 보유하는 변수를 선언합니다.  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### 2차원  
 일부 배열은 교내 각 건물의 각 층에 있는 사무실 수가 들어 있는 배열과 같이 2차원 배열입니다.  요소를 지정할 때는 건물 번호와 층이 모두 필요하며 각 요소가 건물과 층의 조합에 대한 카운트를 보유해야 합니다.  따라서 이러한 배열에서는 두 개의 인덱스를 사용합니다.  다음 예제에서는 건물 0~ 40과 층 0~5에 대한 사무실 카운트가 들어 있는 *2차원 배열*을 보유하는 변수를 선언합니다.  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 2차원 배열을 *사각형 배열*이라고도 합니다.  
  
### 3차원  
 일부 배열은 3차원 공간의 값이 들어 있는 배열과 같이 3차원 배열입니다.  이러한 배열에서는 세 개의 인덱스를 사용하며 위 배열의 경우 각 인덱스는 물리적 공간의 x, y 및 z 좌표를 나타냅니다.  다음 예제에서는 3차원 공간의 여러 지점에서 측정한 온도가 들어 있는 *3차원 배열*을 보유하는 변수를 선언합니다.  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### 4차원 이상  
 배열에는 최대 32개의 차원이 있을 수 있지만 4차원 이상을 사용하는 경우는 거의 없습니다.  
  
> [!NOTE]
>  배열에 차원을 추가하면 배열에 필요한 전체 저장 공간이 상당히 늘어나므로 다차원 배열은 신중하게 사용해야 합니다.  
  
## 다른 차원 사용  
 현재 월의 매일 총 판매액을 추적하려는 경우  다음 예제와 같이 해당 월의 각 날짜에 해당하는 31개의 요소가 있는 1차원 배열을 선언할 수 있습니다.  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 특정 달의 모든 날짜뿐 아니라 특정 연도의 모든 월에 대해서도 동일한 정보를 추적하려는 경우  다음 예제와 같이 월을 나타내는 12개의 행과 날짜를 나타내는 31개의 열이 있는 2차원 배열을 선언할 수 있습니다.  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 1년 이상의 기간에 대한 정보를 보유하는 배열을 만들 수도 있습니다.  예를 들어, 5년 동안의 총 판매액을 추적하려는 경우 다음 예제와 같이 5개의 레이어, 12개의 행 및 31개의 열이 있는 3차원 배열을 선언할 수 있습니다.  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 각 인덱스는 0부터 최대값까지 변화하므로 `salesAmounts`의 각 차원은 해당 차원에 필요한 길이보다 1만큼 작게 선언됩니다.  배열의 크기는 새 차원을 추가할 때마다 증가합니다.  위 예제에서 세 차원의 크기\(요소 수\)는 각각 31, 372 및 1,860입니다.  
  
> [!NOTE]
>  `Dim` 문 또는 `New` 절을 사용하지 않고도 배열을 만들 수 있습니다.  예를 들어, <xref:System.Array.CreateInstance%2A> 메서드를 호출하거나 다른 구성 요소에서 코드에 이 방식으로 만든 배열을 전달할 수 있습니다.  이러한 배열의 하한은 0이 아닐 수 있습니다.  언제든지 <xref:System.Array.GetLowerBound%2A> 메서드나 `LBound` 함수를 사용하여 차원의 하한을 테스트할 수 있습니다.  
  
## 참고 항목  
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Troubleshooting Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)