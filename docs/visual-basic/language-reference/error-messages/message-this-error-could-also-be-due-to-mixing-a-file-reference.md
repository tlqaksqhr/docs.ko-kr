---
title: "&lt;메시지&gt; 어셈블리 &#39;에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문에이 오류도 수&lt; assemblyname&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords: BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a30e5d5aca09e7b74e16dd05cdc0c5c361c1657d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a>&lt;메시지&gt; 어셈블리 &#39;에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문에이 오류도 수&lt; assemblyname&gt;&#39;
\<메시지 > 어셈블리에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문에이 오류도 수 '\<assemblyname > 합니다. 이 경우에 대 한 파일 참조를 바꿔를 보십시오 '\<assemblyfilename >' 프로젝트에서 '\<projectname1 >'에 대 한 프로젝트 참조 '\<projectname2 >'입니다.  
  
 프로젝트 코드에서 다른 프로젝트의 멤버에 액세스하지만 솔루션 구성상 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러에서 참조를 확인할 수 없습니다.  
  
 다른 어셈블리에 정의된 형식에 액세스하려면 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러에 해당 어셈블리에 대한 참조가 있어야 합니다. 이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.  
  
 **오류 ID:** BC30971  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다. 이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.  
  
2.  프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 프로젝트에 대한 참조를 추가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)  
 [선언된 요소 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)  
 [끊어진 참조 문제 해결](/visualstudio/ide/troubleshooting-broken-references)
