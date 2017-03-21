---
title: "런타임에 바인딩을된 확인 합니다. 런타임 오류가 발생할 수 있습니다 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
dev_langs:
- VB
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
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
ms.openlocfilehash: 3ac885b0de2c4f44d4323487fc55cde9b23defa4
ms.lasthandoff: 03/13/2017

---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>런타임에 바인딩을 확인합니다. 런타임 오류가 발생할 수 있습니다.
으로 선언 된 변수에 개체 할당 되는 [Object 데이터 형식](../../../visual-basic/language-reference/data-types/object-data-type.md)합니다.  
  
 변수를 선언할 때 `Object`, 컴파일러에서 수행 해야 *런타임에 바인딩*, 실행 시 추가 작업에 이르게 됩니다. 또한 응용 프로그램이 잠재적인 런타임 오류에 노출됩니다. 예를 들어, 할당 하는 경우는 <xref:System.Windows.Forms.Form>에 `Object` 변수와 액세스는 <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName>속성을 런타임에 throw는 <xref:System.MemberAccessException>때문에 <xref:System.Windows.Forms.Form>클래스에서 노출 하지는 `NameTable` 속성.</xref:System.Windows.Forms.Form> </xref:System.MemberAccessException> </xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName> </xref:System.Windows.Forms.Form>  
  
 특정 형식의 변수를 선언 하면 컴파일러에서 수행할 수 *초기 바인딩* 컴파일 타임에 있습니다. 이 인해 성능 향상된, 특정 형식의 멤버를 코드의 가독성을 높이기 액세스를 제어 합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC42017  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   가능 하면 특정 형식의 변수를 선언 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [초기 바인딩 및 런타임에 바인딩](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)   
 [개체 변수 선언](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
