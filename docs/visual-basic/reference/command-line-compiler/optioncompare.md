---
title: "/optioncompare | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioncompare
dev_langs:
- VB
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
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
ms.openlocfilehash: 53dee5bb50e20204725f031e3e04f5c37c5b3f96
ms.lasthandoff: 03/13/2017

---
# <a name="optioncompare"></a>/optioncompare
문자열 비교 방법을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a>주의  
 지정할 수 있습니다 `/optioncompare` 두 가지 형태 중 하나: `/optioncompare:binary` 이진 문자열 비교를 사용 하 여 및 `/optioncompare:text` 텍스트 문자열 비교를 사용 하도록 합니다. 기본적으로 컴파일러는 다음과 같이 사용 됩니다. `/optioncompare:binary`합니다.  
  
 Microsoft Windows에서 사용 되는 코드 페이지는 이진 정렬 순서를 결정 합니다. 일반적인 이진 정렬 순서는 다음과 같습니다.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 텍스트 기반 문자열 비교는 시스템의 로캘에 따라 결정 되는 대/소문자 구분 텍스트 정렬 순서를 기준으로 합니다. 일반적인 텍스트 정렬 순서는 다음과 같습니다.  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a>Visual Studio IDE에서 /optioncompare를 설정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.  
  
2.  클릭 하 고 **컴파일** 탭 합니다.  
  
3.  값을 수정 된 **Option Compare** 상자입니다.  
  
### <a name="to-set-optioncompare-programmatically"></a>/Optioncompare를 프로그래밍 방식으로 설정 하려면  
  
-   참조 [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 P를 컴파일하여`rojFile.vb` 컴파일하고 이진 문자열 비교를 사용 합니다.  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [옵션 대화 상자, 프로젝트, Visual Basic 기본값](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
