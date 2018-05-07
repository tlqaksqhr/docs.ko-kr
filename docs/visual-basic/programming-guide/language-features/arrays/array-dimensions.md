---
title: Array Dimensions in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: cf295288dd034d744dceb71b5c58278be5cc2a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="array-dimensions-in-visual-basic"></a>Array Dimensions in Visual Basic
A *차원* 은 방향 배열 요소의 사양을 변경할 수 있습니다. 각 날짜의 월에 대 한 총 판매를 포함 하는 배열에는 1 차원 (해당 월의 일)에 있습니다. 총 판매액이 들어 부서별로 각 날짜의 월에 대 한 배열 차원이 두 개 (부서 번호 및 월의 일). 배열의 차원 수 라고 해당 *순위*합니다.  
  
> [!NOTE]
>  사용할 수는 <xref:System.Array.Rank%2A> 배열이 차원 수를 결정 하는 속성입니다.  
  
## <a name="working-with-dimensions"></a>차원 작업  
 배열의 요소를 제공 하 여 지정 된 *인덱스* 또는 *아래 첨자* 배열의 각 차원에 대 한 합니다. 요소는 해당 차원에 대 한 가장 높은 인덱스를 인덱스 0에서에서 각 차원에 따라 연속입니다.  
  
 다음 그림의 순위에 다른 배열 개념적 구조를 보여줍니다. 각 요소는 그림에 액세스 하는 인덱스 값을 보여 줍니다. 예를 들어 2 차원 배열의 두 번째 행의 첫 번째 요소 인덱스를 지정 하 여 액세스할 수 있습니다 `(1, 0)`합니다.  
  
 ![하나는 그래픽 다이어그램&#45;차원 배열](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")  
1 차원 배열  
  
 ![2의 그래픽 다이어그램&#45;차원 배열](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")  
2 차원 배열  
  
 ![세 개의의 그래픽 다이어그램&#45;차원 배열](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")  
3 차원 배열  
  
### <a name="one-dimension"></a>차원이 두 개  
 많은 배열을는 각 나이 사용자 수와 같이 차원이 하나만 있어야 합니다. 요소를 지정 하는 유일한 요구 사항은 나가는 해당 요소의 개수를 보유 합니다. 따라서 이러한 배열 인덱스는 하나만 사용합니다. 다음 예제에서는 선언 보유 하는 변수는 *1 차원 배열* age의 나가 120 사이의 0에 대 한 계산 합니다.  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a>2 차원  
 일부 배열은 있는 캠퍼스 각 건물의 각 층에서 사무실의 수와 같은 두 개의 차원입니다. 요소를 지정할 건물 번호와 층이 모두를 차지 하며 각 요소를 함께 건물과 층의 개수를 보유 합니다. 따라서 이러한 배열에서는 두 개의 인덱스를 사용 합니다. 다음 예제에서는 보유 하는 변수를 선언는 *2 차원 배열* 0 ~ 40 건물과 층 0 ~ 5에 대 한 office 카운트 합니다.  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 2 차원 배열을 라고도 *사각형 배열을*합니다.  
  
### <a name="three-dimensions"></a>3 차원  
 몇 가지 배열은 있는 3d 공간에서 값과 같은 3 차원입니다. 이러한 배열은 경우 x, y 및 z 좌표 물리적 공간을 나타내는 세 개의 인덱스를 사용 합니다. 다음 예제에서는 보유 하는 변수를 선언는 *3 차원 배열을* 한 다양 한 시점에서 차원 공간의 온도가 합니다.  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a>4 개 이상의 차원  
 배열 32 차원을 수 있지만에 거의 3 개를 초과 합니다.  
  
> [!NOTE]
>  배열에 차원을 추가 하면 상당히 다차원 배열은 주의 하 여 배열에 필요한 총 저장소 증가 합니다.  
  
## <a name="using-different-dimensions"></a>다른 차원 사용  
 현재 월의 모든 날에 대 한 판매 금액을 추적 하 고 한다고 가정 합니다. 다음 예제와 같이 해당 월의 각 날짜에 대 한 한 표시 31 요소는 1 차원 배열을 선언할 수 있습니다.  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 이제 한 달의 뿐만 아니라 해당 연도의 매월을 매일 뿐만 아니라 동일한 정보를 추적 하려는 경우 다음과 같이 합니다. 다음 예제와 같이 (개월)에 대 한 12 개의 행과 31 열 일)에 대 한 2 차원 배열을 선언할 수 있습니다.  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 현재 사용 하기로 결정할 경우를 가정해 볼 배열 1 년 이상에 대 한 정보를 포함 합니다. 5 년에 대 한 총 판매액을 추적 하려는 경우 다음 예제와 같이 5 개의 레이어, 12 개의 행과 31 열이 있는 3 차원 배열을 선언할 수 있습니다.  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 각 인덱스 0에서 최대값의 각 차원 다릅니다 때문에 `salesAmounts` 해당 차원에 필요한 길이 보다 1 작은 값으로 선언 됩니다. 배열의 크기 각 새 차원에 따라 카운터가 증가 또한 note 합니다. 이전 예제에서 세 가지 크기만 각각 31, 372, 및 1,860 요소입니다.  
  
> [!NOTE]
>  사용 하지 않고 배열을 만들 수는 `Dim` 문 또는 `New` 절. 예를 들어, 호출할 수 있습니다는 <xref:System.Array.CreateInstance%2A> 메서드 또는 다른 구성 요소 배열을 전달할 수 코드 이런이 방식으로 생성 합니다. 이러한 배열은 0이 아닌 있을 수 있습니다. 사용 하 여 차원의 최소치 항상 테스트할 수 있습니다는 <xref:System.Array.GetLowerBound%2A> 메서드 또는 `LBound` 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [배열 문제 해결](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
