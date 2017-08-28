---
title: "-noconfig(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /noconfig
dev_langs:
- CSharp
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 594e972dc834ab74412e30a48428f850ae02b5ac
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="noconfig-c-compiler-options"></a>/noconfig(C# 컴파일러 옵션)
**/noconfig** 옵션은 csc.exe 파일과 동일한 디렉터리에 있고 여기서 로드되는 csc.rsp 파일로 컴파일하지 않도록 컴파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```console  
/noconfig  
```  
  
## <a name="remarks"></a>설명  
 csc.rsp 파일은 .NET Framework와 함께 제공되는 모든 어셈블리를 참조합니다. Visual Studio .NET 개발 환경에 포함된 실제 참조는 프로젝트 형식에 따라 달라집니다.  
  
 csc.rsp 파일을 수정하여 **/noconfig** 옵션을 제외하고 csc.exe를 사용하여 명령줄에서 컴파일할 때마다 포함되어야 하는 추가 컴파일러 옵션을 지정할 수 있습니다.  
  
 컴파일러는 **csc** 명령에 마지막으로 전달된 옵션을 처리합니다. 따라서 명령줄의 모든 옵션은 csc.rsp 파일에 있는 동일한 옵션의 설정을 재정의합니다.  
  
 컴파일러가 csc.rsp 파일의 설정을 찾아서 사용하지 않도록 하려면 **/noconfig**를 지정합니다.  
  
 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)   
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)

