---
title: "비-CLS 규격 &lt;membername&gt; CLS 규격 인터페이스에서 허용 되지 않는 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
dev_langs:
- VB
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 9
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
ms.openlocfilehash: 2861ef22c9307e5bd7d2eabf4f6e37bbd9086345
ms.lasthandoff: 03/13/2017

---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>비-CLS 규격 &lt;membername&gt; CLS 비규격 인터페이스를 사용할 수 없습니다
속성, 프로시저 또는 인터페이스의 이벤트로 표시 되어 `<CLSCompliant(True)>` 인터페이스 자체로 표시 되 면 `<CLSCompliant(False)>` 또는 표시 되어 있지 않습니다.  
  
 호환 되어야 하는 인터페이스는 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) CLS ()를 모든 해당 멤버 호환 되어야 합니다.  
  
 적용 하는 경우는 <xref:System.CLSCompliantAttribute>특성의 프로그래밍 요소에 설정한 `isCompliant` 매개 변수를 `True` 또는 `False` 준수 여부를 나타냅니다.</xref:System.CLSCompliantAttribute> 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 적용 되지 않은 경우는 <xref:System.CLSCompliantAttribute>요소에 비호환 상태로 간주 됩니다.</xref:System.CLSCompliantAttribute>  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40033  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   CLS 규격 필요 하 고 인터페이스 소스 코드 제어 하는 경우 표시 인터페이스 `<CLSCompliant(True)>` 의 모든 멤버는 호환 되는 경우.  
  
-   CLS 규격이 필요 하 고 인터페이스 소스 코드를 제어할 수 없는 경우 또는 호환 되도록 한정 하지 않는 경우이 멤버는 다른 인터페이스 내에서 정의 합니다.  
  
-   이 멤버는 현재 인터페이스 내에서 남아 있는지 필요로 하는 경우 제거는 <xref:System.CLSCompliantAttribute>정의에서 표시 하거나 `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute>  
  
## <a name="see-also"></a>참고 항목  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [\<통해 PAVE > CLS 규격 코드 작성](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
