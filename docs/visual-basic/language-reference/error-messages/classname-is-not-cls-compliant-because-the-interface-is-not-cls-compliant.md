---
title: "&quot;&lt;classname&gt;&quot; CLS 호환 되지 않는다는 인터페이스 &quot;&lt;interfacename&gt;&quot; 그 구현 CLS 규격이 아닙니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40029
- vbc40029
dev_langs:
- VB
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
caps.latest.revision: 13
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
ms.openlocfilehash: 1e5c948ed5ddeaa2f8a8efd4aa83a2539cc862f3
ms.lasthandoff: 03/13/2017

---
# <a name="39ltclassnamegt39-is-not-cls-compliant-because-the-interface-39ltinterfacenamegt39-it-implements-is-not-cls-compliant"></a>'&lt;classname&gt;' CLS 호환 되지 않는다는 인터페이스 '&lt;interfacename&gt;' 그 구현 하는 CLS 규격이 아닙니다
클래스 또는 인터페이스가 `<CLSCompliant(True)>` 로 표시 또는 표시되지 않은 형식을 구현하거나 해당 형식에서 파생될 때 `<CLSCompliant(False)>` 로 표시되었습니다.  
  
 클래스 또는 인터페이스와 호환 되도록는 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) CLS (), 전체 상속 계층 구조 호환 되어야 합니다. 즉, 직접이든 간접이든 상속하는 모든 형식이 규격을 준수해야 한다는 의미입니다. 마찬가지로 클래스가 하나 이상의 인터페이스를 구현하는 경우 해당 상속 계층 전체가 모두 규격을 준수해야 합니다.  
  
 적용 하는 경우는 <xref:System.CLSCompliantAttribute>특성의 프로그래밍 요소에 설정한 `isCompliant` 매개 변수를 `True` 또는 `False` 준수 여부를 나타냅니다.</xref:System.CLSCompliantAttribute> 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 적용 되지 않은 경우는 <xref:System.CLSCompliantAttribute>요소에 비호환 상태로 간주 됩니다.</xref:System.CLSCompliantAttribute>  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40029  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   CLS 규격이 필요하면 다른 상속 계층 구조에서 이 형식을 정의합니다.  
  
-   제거 해야 합니다.이 형식은 현재 상속 계층 구조 나 구현 체계로 머물러야 하는 경우는 <xref:System.CLSCompliantAttribute>정의에서 표시 하거나 `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute>  
  
## <a name="see-also"></a>참고 항목  
 [\<통해 PAVE > CLS 규격 코드 작성](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
