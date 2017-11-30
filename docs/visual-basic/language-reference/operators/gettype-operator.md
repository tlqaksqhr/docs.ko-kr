---
title: "GetType 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38a984dce44133936f7f163e6afb20f0f336377c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="gettype-operator-visual-basic"></a>GetType 연산자(Visual Basic)
반환 된 <xref:System.Type> 지정된 된 형식에 대 한 개체입니다. <xref:System.Type> 개체의 속성, 메서드 및 이벤트와 같은 형식에 대 한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---|---|  
|`typename`|정보 원하는 형식의 이름입니다.|  
  
## <a name="remarks"></a>설명  
 `GetType` 연산자는 반환 된 <xref:System.Type> 지정 된 개체 `typename`합니다. 에 정의 된 모든 형식의 이름을 전달할 수 있습니다 `typename`합니다. 여기에는 다음과 같은 사항이 포함됩니다.  
  
-   와 같은 모든 Visual Basic 데이터 형식 `Boolean` 또는 `Date`합니다.  
  
-   모든.NET Framework 클래스, 구조체, 모듈 또는 인터페이스와 같은 <xref:System.ArgumentException?displayProperty=nameWithType> 또는 <xref:System.Double?displayProperty=nameWithType>합니다.  
  
-   모든 클래스, 구조체, 모듈 또는 인터페이스 응용 프로그램에서 정의 합니다.  
  
-   응용 프로그램에 정의 된 배열입니다.  
  
-   응용 프로그램에서 정의 된 대리자입니다.  
  
-   Visual Basic,.NET Framework 또는 응용 프로그램에 정의 된 모든 열거형입니다.  
  
 개체 변수의 형식 개체를 가져오려는 경우 사용 하 여는 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 메서드.  
  
 `GetType` 연산자는 다음과 같은 경우에 유용할 수 있습니다.  
  
-   런타임 시 형식에 대 한 메타 데이터에 액세스 해야 합니다. <xref:System.Type> 개체 형식 멤버 및 배포 정보 등의 메타 데이터를 제공 합니다. 해야이 예를 들어 어셈블리를 리플렉션 합니다. 자세한 내용은 <xref:System.Reflection?displayProperty=nameWithType>을 참조하십시오.  
  
-   두 개체 참조가 동일한 형식의 인스턴스를 참조 하는 경우를 확인 하려면 비교 하려고 합니다. 그럴 경우 `GetType` 에 동일한 참조를 반환 <xref:System.Type> 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에 나온은 `GetType` 연산자를 사용에서 합니다.  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
