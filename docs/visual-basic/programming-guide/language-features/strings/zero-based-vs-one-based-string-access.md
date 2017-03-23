---
title: "Vs&0;부터 시작 합니다. Visual Basic에서&1;부터 시작 하는 문자열 액세스 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
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
ms.openlocfilehash: 6cd2cab888bf336151ed26968119431f4ffc75f4
ms.lasthandoff: 03/13/2017

---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Vs&0;부터 시작 합니다. Visual Basic에서&1;부터 시작 하는 문자열 액세스
이 항목에서는 비교 방법을 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 및 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 문자열의 문자에 대 한 액세스를 제공 합니다. [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 항상는 문자열의에서 문자에 대 한&0;부터 시작 액세스를 제공 하지만 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 함수에 따라&0;부터 시작 하 고&1;부터 액세스를 제공 합니다.  
  
## <a name="one-based"></a>1부터 시작  
 1부터 시작 하는 예로 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 함수를 고려해 야는 `Mid` 함수입니다. 부분 문자열이 시작 위치 1부터 시작 하는 문자 위치를 지정 하는 인수를 사용 합니다. [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName>메서드는 문자의 인덱스 부분 문자열을 시작 하려면 문자열 위치 0부터 시작 합니다.</xref:System.String.Substring%2A?displayProperty=fullName> 따라서 "ABCDE" 문자열이 있는 경우 개별 문자 매겨집니다와 함께 사용할 1,2,3,4,5는 `Mid` 함수가 있지만 함께 사용할 0,1,2,3,4는 <xref:System.String.Substring%2A?displayProperty=fullName>메서드.</xref:System.String.Substring%2A?displayProperty=fullName>  
  
## <a name="zero-based"></a>0부터 시작  
 0부터 시작에 대 한 예제 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 함수를 고려해 야는 `Split` 함수입니다. 문자열을 분할 하 고 부분 문자열이 포함 된 배열을 반환 합니다. [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName>메서드는 문자열을 분할 및 부분 문자열이 포함 된 배열을 반환 합니다.</xref:System.String.Split%2A?displayProperty=fullName> 때문에 `Split` 함수 및 <xref:System.String.Split%2A>메서드가 반환 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 배열은&0;부터 시작 해야 합니다.</xref:System.String.Split%2A>  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:System.String.Substring%2A></xref:System.String.Substring%2A>   
 <xref:System.String.Split%2A></xref:System.String.Split%2A>   
 [Visual Basic의 문자열 소개](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
