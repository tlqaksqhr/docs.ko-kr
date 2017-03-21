---
title: "Mid 문 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
dev_langs:
- VB
helpviewer_keywords:
- substrings, Mid statement
- strings [Visual Basic], substrings
- Mid statement
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e385d6838daa16d45903c6b270fc47ad88797845
ms.lasthandoff: 03/13/2017

---
# <a name="mid-statement"></a>Mid 문
문자를 지정 된 개수의 `String` 를 다른 문자열 변수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>요소  
 `Target`  
 필수 요소. 이름에서 `String` 변수를 수정 합니다.  
  
 `Start`  
 필수 요소. `Integer`식입니다. 문자 위치 `Target` 텍스트 교체를 시작 합니다. `Start`1부터 시작 하는 인덱스를 사용 합니다.  
  
 `Length`  
 선택적 요소. `Integer`식입니다. 바꿀 문자 수입니다. 생략 하면 모든 `String` 사용 됩니다.  
  
 `StringExpression`  
 필수 요소. `String`식의 일부를 대체 하는 `Target`합니다.  
  
## <a name="exceptions"></a>예외  
  
|예외 형식|조건|  
|--------------------|---------------|  
|<xref:System.ArgumentException></xref:System.ArgumentException>|`Start`<= 0="" or=""></=>`Length`< 0.></ 0.>|  
  
## <a name="remarks"></a>설명  
 대체 문자 수는 항상의 문자 수가 보다 작거나 `Target`합니다.  
  
 Visual Basic에는 <xref:Microsoft.VisualBasic.Strings.Mid%2A>함수 및 `Mid` 문.</xref:Microsoft.VisualBasic.Strings.Mid%2A> 이러한 요소는 지정된 된 수는 문자열의 문자에 모두 작동 하지만 `Mid` 해당 문자를 반환 하는 함수는 `Mid` 문은 문자를 대체 합니다. 자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</xref:Microsoft.VisualBasic.Strings.Mid%2A> 을 참조 하십시오.  
  
> [!NOTE]
>  `MidB` 이전 버전의 Visual Basic의 문 문자가 아닌 바이트의 하위 문자열을 대체 합니다. 더블 바이트 문자 집합 (DBCS) 응용 프로그램에서 문자열을 변환 하는 데 주로 사용 됩니다. 모든 Visual Basic 문자열은 유니코드에서 및 `MidB` 은 더 이상 지원 합니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `Mid` 문을 다른 문자열에서 지정한 개수의 문자열 변수에 문자를 바꿉니다.  
  
 [!code-vb[VbVbalrStrings #&5;](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>요구 사항  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **모듈:**`Strings`  
  
 **어셈블리:**[!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 [문자열](../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [Visual Basic의 문자열 소개](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
