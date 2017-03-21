---
title: "&lt;메시지&gt; 어셈블리에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문에이 오류도 수 &quot;&lt;assemblyname&gt;&quot; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
dev_langs:
- VB
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a1806fd078fc05d966c718841e5b78c1323a43c2
ms.lasthandoff: 03/13/2017

---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a>&lt;메시지&gt; 어셈블리에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문에이 오류도 수 '&lt;assemblyname&gt;'
\<메시지 >이 오류에도 어셈블리에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문에 수 '\<assemblyname >. 이 경우에 대 한 파일 참조를 교체를 시도 '\<assemblyfilename > ' 프로젝트에서 '\<projectname1 > '에 대 한 프로젝트와 '\<projectname2 > '입니다.  
  
 프로젝트의 코드가 다른 프로젝트의 멤버에 액세스할 수 있지만 솔루션의 구성을 허용 하지 않습니다는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러는 참조를 확인 합니다.  
  
 다른 어셈블리에 정의된 형식에 액세스하려면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에 해당 어셈블리에 대한 참조가 있어야 합니다. 이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.  
  
 **오류 ID:** BC30971  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다. 이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.  
  
2.  프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 프로젝트에 대한 참조를 추가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트에서 참조 관리](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NIB 하는 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [끊어진 참조 문제 해결](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)
