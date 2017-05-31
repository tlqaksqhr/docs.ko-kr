---
title: "-lib(C# 컴파일러 옵션) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /lib
dev_langs:
- CSharp
helpviewer_keywords:
- lib compiler option [C#]
- -lib compiler option [C#]
- /lib compiler option [C#]
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
caps.latest.revision: 16
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 27bcca456a7a5c884c33de6429e06c94afc9536a
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="lib-c-compiler-options"></a>/lib(C# 컴파일러 옵션)
**/lib** 옵션은 [/reference(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 옵션을 통해 참조되는 어셈블리의 위치를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
/lib:dir1[,dir2]  
```  
  
## <a name="arguments"></a>인수  
 `dir1`  
 참조된 어셈블리를 현재 작업 디렉터리(컴파일러를 호출하는 디렉터리) 또는 공용 언어 런타임의 시스템 디렉터리에서 찾을 수 없는 경우 컴파일러에서 확인할 디렉터리입니다.  
  
 `dir2`  
 어셈블리 참조를 검색할 하나 이상의 추가 디렉터리입니다. 이름 사이에 공백 없이 추가 디렉터리 이름을 쉼표로 구분합니다.  
  
## <a name="remarks"></a>설명  
 컴파일러는 정규화되지 않은 어셈블리 참조를 다음 순서대로 검색합니다.  
  
1.  현재 작업 디렉터리입니다. 컴파일러가 호출되는 디렉터리입니다.  
  
2.  공용 언어 런타임 시스템 디렉터리입니다.  
  
3.  **/lib**로 지정된 디렉터리입니다.  
  
4.  LIB 환경 변수로 지정된 디렉터리입니다.  
  
 어셈블리 참조를 지정하려면 **/reference**를 사용합니다.  
  
 **/lib**는 가감되므로 두 번 이상 지정하면 이전 값에 추가됩니다.  
  
 **/lib**를 사용하는 대신 필요한 모든 어셈블리를 작업 디렉터리에 복사할 수도 있습니다. 이렇게 하면 단순히 어셈블리 이름을 **/reference**에 전달할 수 있습니다. 그런 다음 작업 디렉터리에서 어셈블리를 삭제할 수 있습니다. 종속 어셈블리의 경로는 어셈블리 매니페스트에 지정되지 않으므로 응용 프로그램이 대상 컴퓨터에서 시작될 수 있으며, 전역 어셈블리 캐시에서 어셈블리를 찾아 사용합니다.  
  
 컴파일러가 어셈블리를 참조할 수 있다고 해서 공용 언어 런타임이 런타임에 어셈블리를 찾아 로드할 수 있다는 의미는 아닙니다. 런타임에서 참조된 어셈블리를 검색하는 방법에 대한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하세요.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  
  
2.  **참조 경로** 속성 페이지를 클릭합니다.  
  
3.  목록 상자 내용을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>를 참조하세요.  
  
## <a name="example"></a>예제  
 t2.cs를 컴파일하여 .exe 파일을 만듭니다. 컴파일러는 작업 디렉터리 및 C 드라이브의 루트 디렉터리에서 어셈블리 참조를 찾습니다.  
  
```console  
csc /lib:c:\ /reference:t2.dll t2.cs  
```  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
