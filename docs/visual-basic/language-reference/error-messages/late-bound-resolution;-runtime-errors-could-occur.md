---
title: "런타임에 바인딩을 확인합니다. 런타임 오류가 발생할 수 있습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords: BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d01164914b484ef689654f048a8743f3c2eb669
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>런타임에 바인딩을 확인합니다. 런타임 오류가 발생할 수 있습니다.
개체도 선언 된 변수에 할당 되는 [Object 데이터 형식](../../../visual-basic/language-reference/data-types/object-data-type.md)합니다.  
  
 변수를 선언할 때 `Object`, 컴파일러에서 수행 해야 *런타임에 바인딩*, 런타임에 추가 작업이 필요 하면 합니다. 또한 응용 프로그램이 잠재적인 런타임 오류에 노출됩니다. 예를 들어, 할당 하는 경우는 <xref:System.Windows.Forms.Form> 에 `Object` 변수에 액세스 하려고 하는 <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> 속성, 런타임에서 throw 한 <xref:System.MemberAccessException> 때문에 <xref:System.Windows.Forms.Form> 클래스를 노출 하지 않습니다는 `NameTable` 속성.  
  
 특정 형식으로 변수를 선언 하면 컴파일러가 수행할 수 *초기 바인딩* 컴파일 타임에 있습니다. 이 인해 성능 향상된, 특정 형식의 멤버 및 코드의 가독성을 높이기에 액세스를 제어 합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC42017  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   가능한 경우 특정 형식으로 변수를 선언 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [초기 바인딩 및 런타임에 바인딩](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [개체 변수 선언](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
