---
title: "유형 &quot;&lt;typename&gt;&quot;가 정의 되지 않은 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
dev_langs:
- VB
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 09aa7c535fd5e17ddcd0e743fb5ec17ebadd4f7d
ms.lasthandoff: 03/13/2017

---
# <a name="type-39lttypenamegt39-is-not-defined"></a>유형 '&lt;typename&gt;' 정의 되어 있지 않습니다
문이 정의 되지 않은 형식에 대 한 참조를 했습니다. 선언문에서와 같은 형식을 정의할 수 `Enum`, `Structure`, `Class`, 또는 `Interface`합니다.  
  
 **오류 ID:** BC30002  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   형식 정 및 참조 둘 다 사용 하는 철자를 확인 합니다.  
  
-   형식 정의 대 한 참조에 액세스할 수 있는지 확인 합니다. 예를 들어, 형식이 다른 모듈에서 선언 된 경우 `Private`, 참조 하는 모듈로 형식 정의 이동 하거나 선언 `Public`합니다.  
  
-   형식의 네임 스페이스 프로젝트 내에서 다시 정의 되지 않는지 확인 합니다. 인 경우 사용 된 `Global` 형식 이름을 정규화 하는 키워드입니다. 예를 들어, 프로젝트 이름은 네임 스페이스를 정의 하는 경우 `System`, <xref:System.Object?displayProperty=fullName>하지 않은 경우 정규화 된 형식에 액세스할 수 없습니다는 `Global` 키워드: `Global.System.Object`.</xref:System.Object?displayProperty=fullName>  
  
-   형식이 정의 되어 있지만 개체 라이브러리 또는 정의 된 형식 라이브러리에 등록 되지 않은 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 클릭 **참조 추가** 에 **프로젝트** 메뉴 한 다음 적절 한 개체 라이브러리 또는 형식 라이브러리를 선택 합니다.  
  
-   대상된.NET Framework 프로필의 일부인 어셈블리에서 형식 인지 확인 합니다. 자세한 내용은 참조 [.NET Framework 대상 지정 오류 문제 해결](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [프로젝트의 참조 관리](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)
