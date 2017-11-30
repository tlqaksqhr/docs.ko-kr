---
title: "비 CLS 규격 &lt;membername&gt; CLS 규격 인터페이스에서는 허용 되지 않습니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords: BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 358abd338d3ce780c2f0aae7aa8efb53e57b477c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>비 CLS 규격 &lt;membername&gt; CLS 규격 인터페이스에서는 허용 되지 않습니다
속성, 프로시저 또는 인터페이스의 이벤트로 표시 되어 `<CLSCompliant(True)>` 인터페이스 자체로 표시 되 면 `<CLSCompliant(False)>` 되거나 표시 되지 않습니다.  
  
 과 호환 되도록 인터페이스는 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) (CLS) 모든 해당 멤버 규정을 준수 해야 합니다.  
  
 <xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40033  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   CLS 규격이 필요 하 고 인터페이스의 소스 코드에 대 한 제어 하지 않는 경우 표시할 인터페이스 `<CLSCompliant(True)>` 모든 해당 멤버 호환 되는 경우.  
  
-   CLS 규격이 필요 하 고 인터페이스의 소스 코드를 제어할 수 없는 경우 또는 규격이 되려면 맞지 않을 경우 다른 인터페이스 내에서이 멤버를 정의 합니다.  
  
-   이 멤버는 현재 인터페이스 내에 유지 하려면, 제거는 <xref:System.CLSCompliantAttribute> 해당 정의에서 표시 하거나 `<CLSCompliant(False)>`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [\<통해 PAVE > CLS 규격 코드 작성](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
