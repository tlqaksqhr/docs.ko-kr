---
title: "#<a name=\"region-directive\"></a>Region 지시문"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb308da6ad0ca6243f14e0d825ed7eb005d622bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="region-directive"></a>#Region 지시문
Visual Basic 파일에서 코드 섹션을 축소하고 숨깁니다.  
  
## <a name="syntax"></a>구문  
  
```  
      #Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`identifier_string`|필수 요소. 축소된 경우 영역의 제목 역할을 하는 문자열입니다. 영역은 기본적으로 축소되어 있습니다.|  
|`#End Region`|`#Region` 블록을 종료합니다.|  
  
## <a name="remarks"></a>설명  
 `#Region` 지시문을 사용하면 Visual Studio 코드 편집기의 개요 기능을 사용할 때 확장하거나 축소할 코드 블록을 지정할 수 있습니다. 배치할 수 있습니다 또는 *중첩*, 비슷한 영역을 그룹화 하 여 다른 영역 들 내 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `#Region` 지시문을 사용합니다.  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [#If...Then...#Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [개요](/visualstudio/ide/outlining)  
 [방법: 코드 섹션 축소 및 숨기기](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
