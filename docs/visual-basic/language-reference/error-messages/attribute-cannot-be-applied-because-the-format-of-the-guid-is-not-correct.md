---
title: "&quot;&lt;특성&gt;&quot; 때문에 적용할 수 없습니다 GUID의 형식은 &quot;&lt;번호&gt;&quot; 올바르지 않은 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32500
- bc32500
dev_langs:
- VB
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: 10
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
ms.openlocfilehash: f22f9ecd63582e2a346702919cf9154819b8eb0e
ms.lasthandoff: 03/13/2017

---
# <a name="39ltattributegt39-cannot-be-applied-because-the-format-of-the-guid-39ltnumbergt39-is-not-correct"></a>'&lt;특성&gt;' 때문에 적용할 수 없습니다 GUID의 형식은 '&lt;번호&gt;' 올바르지 않은
A `COMClassAttribute` 특성 블록 GUID에 대 한 적절 한 형식에 맞지 않는 전역 고유 식별자 (GUID)를 지정 합니다. `COMClassAttribute`Guid를 사용 하 여 클래스, 인터페이스 및 생성 이벤트를 고유 하 게 식별 합니다.  
  
 GUID는 16바이트로 구성되며, 그중에서 처음 8바이트는 숫자이고 마지막 8바이트는 이진입니다. Uuidgen.exe와 같은 Microsoft 유틸리티에서 생성 하 고 공간 및 시간에 고유 하도록 보장 됩니다.  
  
 **오류 ID:** BC32500  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  COM 개체를 식별 하는 데 필요한 올바른 GUID를 확인 합니다.  
  
2.  `COMClassAttribute` 특성 블록에 제공되는 GUID 문자열이 올바르게 복사되었는지 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Guid></xref:System.Guid>   
[특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)


