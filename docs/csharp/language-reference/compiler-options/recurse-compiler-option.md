---
title: "-recurse(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /recurse
dev_langs:
- CSharp
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
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
ms.openlocfilehash: 99664f8b32f5f9e5bf491c5bfde2c1649de42dd9
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="recurse-c-compiler-options"></a>/recurse(C# 컴파일러 옵션)
/recurse 옵션을 사용하면 지정된 디렉터리(dir) 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일을 컴파일할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```console  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a>인수  
 `dir`(선택 사항)  
 검색을 시작하려는 디렉터리입니다. 지정하지 않으면 프로젝트 디렉터리에서 검색이 시작됩니다.  
  
 `file`  
 검색할 파일입니다. 와일드카드 문자가 허용됩니다.  
  
## <a name="remarks"></a>설명  
 **/recurse** 옵션을 사용하면 지정된 디렉터리(`dir`) 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일을 컴파일할 수 있습니다.  
  
 파일 이름에 와일드카드를 사용하면 **/recurse**를 사용하지 않고 프로젝트 디렉터리에서 일치하는 모든 파일을 컴파일할 수 있습니다.  
  
 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.  
  
## <a name="example"></a>예제  
 현재 디렉터리의 모든 C# 파일을 컴파일합니다.  
  
```console  
csc *.cs  
```  
  
 dir1\dir2 디렉터리와 자식 디렉터리에 있는 모든 C# 파일을 컴파일하여 dir2.dll을 생성합니다.  
  
```console  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)   
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)

