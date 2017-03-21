---
title: "변수 &quot;&lt;variablename&gt;&quot; 값이 할당 된 전에 사용 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
dev_langs:
- VB
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
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
ms.openlocfilehash: 7ad1f392fae2f90e366277b7b531d96011648866
ms.lasthandoff: 03/13/2017

---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a>변수 '&lt;variablename&gt;' 값이 할당 된 전에 사용 하는
변수 '\<variablename > ' 값을 할당 되기 전에 사용 됩니다. 런타임에 null 참조 예외가 발생할 수 있습니다.  
  
 응용 프로그램에 어떤 값이 할당 되기 전에 변수를 읽고 해당 코드를 통해 하나 이상의 경로가 있습니다.  
  
 변수에 값이 할당되지 않으면 해당 데이터 형식에 대한 기본값을 유지합니다. 참조 데이터 형식, 해당 기본값은 [Nothing](../../../visual-basic/language-reference/nothing.md)합니다. 값을 가진 참조 변수를 읽는 `Nothing` 발생할 수 있습니다는 <xref:System.NullReferenceException>에 따라서는.</xref:System.NullReferenceException>  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** b c&42104;  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   제어 흐름 논리를 확인 하 고 변수를 읽는 모든 문으로 제어가 전달 되기 전에 유효한 값에 있는지 확인 하십시오.  
  
-   변수에 올바른 값을 포함 하는 항상 유지 되도록 한 가지 방법은 선언의 일부로 초기화 하는 것입니다. 에 "초기화"를 참조 하십시오. [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [변수 선언](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [변수 문제 해결](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
