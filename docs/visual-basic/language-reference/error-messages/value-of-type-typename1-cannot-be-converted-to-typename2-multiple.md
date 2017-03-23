---
title: "형식의 값 &quot;&lt;typename1&gt;&quot;로 변환할 수 없는&quot;&lt;typename2&gt;&quot; (으) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
dev_langs:
- VB
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
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
ms.openlocfilehash: 732291ce9c4b83bb9fc7e83fbbc2a8da9748db59
ms.lasthandoff: 03/13/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a>형식의 값 '&lt;typename1&gt;'로 변환할 수 없는'&lt;typename2&gt;' (여러 파일 참조)
형식의 값 '\<typename1 > '로 변환할 수 없는 '\<typename2 > '입니다. 형식 불일치에 대 한 파일 참조가 섞여 때문일 수 있습니다 '\<filepath1 > ' 프로젝트에서 '\<projectname1 > '에 대 한 파일 참조와 '\<filepath2 > ' 프로젝트에서 '\<projectname2 > '입니다. 두 어셈블리가 동일하면 동일한 대상을 참조하도록 두 참조를 바꿔 보세요.  
  
 둘 이상의 파일 참조를 어셈블리에 프로젝트를 사용 하면 여기서 상황에서 컴파일러는 형식 간에 변환할 수 보장할 수 없습니다.  
  
 각 파일 참조 한 파일 경로 프로젝트 (일반적으로 DLL 파일)의 출력 파일 이름을 지정합니다. 컴파일러 출력 파일이 같은 원본에서 가져왔는지 또는 동일한 어셈블리의 동일한 버전을 표시 하는 보장할 수 없습니다. 따라서 다른 참조의 유형은 같은 형식 또는 다른 하나의 변환할 수 있는지는 보장할 수 없습니다.  
  
 참조 된 어셈블리는 동일한 어셈블리 id를 알고 있는 경우 단일 파일 참조를 사용할 수 있습니다. *어셈블리 ID* 에는 어셈블리 이름, 버전, 공개 키(있는 경우) 및 문화권이 포함됩니다. 이 정보는 어셈블리를 고유하게 식별합니다.  
  
 **오류 ID:** BC30961  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   참조 된 어셈블리 id가 동일한 어셈블리를 제거 하거나 단일 파일 참조만 되도록 파일 참조 중 하나를 바꿉니다.  
  
-   참조 된 어셈블리를 동일한 어셈블리 id 없는 경우 형식에서 다른 형식으로 변환 하려고 하지 않도록 코드를 변경 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 형식 변환](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [프로젝트에서 참조 관리](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
