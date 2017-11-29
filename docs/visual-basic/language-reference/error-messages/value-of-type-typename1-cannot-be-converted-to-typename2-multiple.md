---
title: "형식 &#39;의 값 &lt;typename1&gt;&#39; 변환할 수 없습니다 &#39;&lt; typename2&gt;&#39; (으)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords: BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc6138c7a7ca7d50a56fdd1f536e8d2dc3462a08
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a>형식 &#39;의 값 &lt;typename1&gt;&#39; 변환할 수 없습니다 &#39;&lt; typename2&gt;&#39; (으)
형식의 값 '\<typename1 >'로 변환할 수 없습니다 '\<typename2 >'입니다. 형식 불일치에 대 한 파일 참조가 섞여 있기 때문일 '\<filepath1 >' 프로젝트에서 '\<projectname1 >'에 대 한 파일 참조와 '\<filepath2 >' 프로젝트에서 '\<projectname2 >'입니다. 두 어셈블리가 동일하면 동일한 대상을 참조하도록 두 참조를 바꿔 보세요.  
  
 프로젝트의 어셈블리에 대 한 둘 이상의 파일 참조는 있는 경우에서 컴파일러는 하나의 유형 간에 변환할 수 보장할 수 없습니다.  
  
 각 파일 참조는 프로젝트 (일반적으로 DLL 파일)의 출력 파일의 이름과 파일 경로 지정합니다. 컴파일러 출력 파일이 같은 원본에서 가져왔는지 또는 동일한 어셈블리의 동일한 버전을 표시 하는 보장할 수 없습니다. 따라서 다른 참조의 종류는 동일한 형식 또는 다른 하나의 변환할 수는 보장할 수 없습니다.  
  
 참조 된 어셈블리는 동일한 어셈블리 id를 알고 있는 경우 단일 파일 참조를 사용할 수 있습니다. *어셈블리 ID* 에는 어셈블리 이름, 버전, 공개 키(있는 경우) 및 문화권이 포함됩니다. 이 정보는 어셈블리를 고유하게 식별합니다.  
  
 **오류 ID:** BC30961  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   참조 된 어셈블리 id가 동일한 어셈블리를 제거 하거나 단일 파일 참조만 되도록 파일 참조 중 하나를 바꿉니다.  
  
-   참조 된 어셈블리는 동일한 어셈블리 id가 사용 하지 않으면 다른 형식으로의 형식을 변환 하려고 하지 않도록 코드를 변경 하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 형식 변환](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)  
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
