---
title: "암시적으로 변환 &quot;&lt;typename1&gt;&quot;to&quot;&lt;typename2&gt;ByRef&quot; 매개 변수 값을 복사 하 는&quot; 에서&quot;&lt;parametername&gt;&quot; 일치 하는 인수에 다시 합니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
dev_langs:
- VB
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e397241aab78e17ea4efde0ea682d0e237fb8f8a
ms.lasthandoff: 03/13/2017

---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>암시적으로 변환 '&lt;typename1&gt;'to'&lt;typename2&gt;ByRef' 매개 변수 값을 복사 하 는' 에서'&lt;parametername&gt;' 일치 하는 인수에 다시 합니다.
프로시저를 호출는 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) 해당 매개 변수의 형식과 다른 형식의 인수입니다.  
  
 인수를 전달 하는 경우 `ByRef`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 로컬 변수에 대 한 참조를 전달 하는 대신 프로시저에 인수 값을 복사 합니다. 이 경우, 프로시저에서 반환 하는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 지역 변수 값은 호출 코드에서 인수에 다시 복사 해야 합니다.  
  
 `ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다. 그러나 형식이 서로 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 양방향으로 변환 해야 합니다. 사용할 수 없으므로 `CType` 또는 다른 변환 키워드 프로시저 인수 또는 매개 변수, 이러한 변환에 항상 암시적입니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC41999  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   따라서 프로시저 매개 변수로 동일한 형식의 호출 인수를 가능 하면 사용 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 변수와 필요 하지 않습니다.  
  
-   인수로 사용 하 여 프로시저를 호출 하는 경우 형식 매개 변수 형식과 다를 수 있지만 매개 변수를 정의 호출 인수에 값을 반환할 필요가 없습니다 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 대신 `ByRef`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [프로시저 매개 변수 및 인수](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [값 및 참조로 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
