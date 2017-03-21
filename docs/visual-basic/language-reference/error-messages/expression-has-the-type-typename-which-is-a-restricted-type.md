---
title: "식에는 형식이 &quot;&lt;typename&gt;&quot; 제한 된 형식 및 &quot; Object &quot; 또는 &quot;&quot;에서 상속 된 멤버에 액세스를 사용할 수 있는 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc31393
- vbc31393
dev_langs:
- VB
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: aaedfd825889498159f92cbd1d615cc0064973d3
ms.lasthandoff: 03/13/2017

---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a>식에는 형식이 '&lt;typename&gt;' 제한 된 유형의 이며 ' Object ' 또는 ''에서 상속 된 멤버 액세스에 사용할 수 없습니다
식을 공용 언어 런타임 (CLR) 하 여 boxed 없습니다 하는 형식으로 계산 되지만 boxing을 필요로 하는 멤버에 액세스 합니다.  
  
 *Boxing* 하는 형식을 변환 하는 데 필요한 처리를 말합니다 `Object` 또는 <xref:System.ValueType>.</xref:System.ValueType> 하는 경우에 따라 공용 언어 런타임에서 특정 구조 종류를 예를 들어 상자 없습니다 <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, 및 <xref:System.TypedReference>.</xref:System.TypedReference> </xref:System.RuntimeArgumentHandle> </xref:System.ArgIterator>  
  
 사용 하 여 제한 된 형식에서 상속 된 메서드를 호출 합니다.이 식은 시도 <xref:System.Object>또는 <xref:System.ValueType>, <xref:System.Object.GetHashCode%2A>또는 <xref:System.Object.ToString%2A>.</xref:System.Object.ToString%2A> </xref:System.Object.GetHashCode%2A> 같은</xref:System.ValueType> </xref:System.Object> 이 메서드에 액세스 하려면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 이 오류가 발생 하는 암시적 boxing 변환을 시도 합니다.  
  
 **오류 ID:** BC31393  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  제시된 형식으로 계산되는 식을 찾습니다.  
  
2.  <xref:System.Object>또는 <xref:System.ValueType>.</xref:System.ValueType> </xref:System.Object> 에서 상속 된 메서드를 호출 하려고 하는 문의 부분을 찾습니다  
  
3.  메서드 호출을 방지 하는 문을 다시 작성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
