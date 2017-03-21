---
title: "&quot;&lt;interfacename&gt;.&lt; membername&gt;&quot;가 이미 구현 된 기본 클래스에서 &quot;&lt;baseclassname&gt;&quot;. 재구현 &lt;형식&gt; 가정 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42015
- bc42015
dev_langs:
- VB
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 12
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
ms.openlocfilehash: 5ab2041826f74fdc5aceab7b1ceb26563d9b3f0a
ms.lasthandoff: 03/13/2017

---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a>'&lt;interfacename&gt;.&lt; membername&gt;'가 이미 구현 된 기본 클래스에서 '&lt;baseclassname&gt;'. 재구현 &lt;형식&gt; 가정
속성, 프로시저 또는 파생된 클래스에서 이벤트를 사용 하는 `Implements` 절을 기본 클래스에서 이미 구현 된 인터페이스 멤버를 지정 합니다.  
  
 파생 클래스는 기본 클래스에 의해 구현된 인터페이스 멤버를 다시 구현할 수 있습니다. 이는 기본 클래스 구현 재정의와 다릅니다. 자세한 내용은 참조 [구현](../../../visual-basic/language-reference/statements/implements-clause.md)합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC42015  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   인터페이스 멤버를 다시 구현하려는 경우 어떤 조치도 취할 필요가 없습니다. 파생된 클래스에서 코드를 사용 하지 않으면 재구현된 멤버에 액세스는 `MyBase` 키워드를 기본 클래스 구현에 액세스 합니다.  
  
-   인터페이스 멤버를 다시 구현하지 않으려는 경우 속성, 프로시저 또는 이벤트 선언에서 `Implements` 절을 제거합니다.  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
