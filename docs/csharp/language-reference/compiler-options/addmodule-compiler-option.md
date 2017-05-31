---
title: "-addmodule(C# 컴파일러 옵션) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /addmodule
dev_langs:
- CSharp
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: 13
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
ms.openlocfilehash: 614dbefbb472ef2cd03fcb1ba7a44f08c450bf4a
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="addmodule-c-compiler-options"></a>/addmodule(C# 컴파일러 옵션)
이 옵션은 target:module 스위치로 만들어진 모듈을 현재 컴파일에 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/addmodule:file[;file2]  
```  
  
## <a name="arguments"></a>인수  
 `file`, `file2`  
 메타데이터를 포함하는 출력 파일입니다. 파일에 어셈블리 매니페스트를 포함할 수 없습니다. 둘 이상의 파일을 가져오려면 파일 이름을 쉼표 또는 세미콜론으로 구분합니다.  
  
## <a name="remarks"></a>설명  
 **/addmodule**을 사용하여 추가된 모든 모듈은 런타임에 출력 파일과 동일한 디렉터리에 있어야 합니다. 즉, 컴파일 시간에 임의 디렉터리에 있는 모듈을 지정할 수 있지만 런타임에 모듈이 응용 프로그램 디렉터리에 있어야 합니다. 런타임에 모듈이 응용 프로그램 디렉터리에 없는 경우 <xref:System.TypeLoadException>이 발생합니다.  
  
 `file`에 어셈블리를 사용할 수 없습니다. 예를 들어 [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)을 사용하여 출력 파일이 만들어진 경우 **/addmodule**을 사용하여 해당 메타데이터를 가져올 수 있습니다.  
  
 출력 파일이 **/target:module** 이외의 **/target** 옵션으로 만들어진 경우 **/addmodule**을 사용하여 해당 메타데이터를 가져올 수 없지만 [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)를 사용하여 가져올 수 있습니다.  
  
 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없습니다. 프로젝트에서 모듈을 참조할 수 없습니다. 또한 이 컴파일러 옵션은 프로그래밍 방식으로 변경할 수 없습니다.  
  
## <a name="example"></a>예제  
 소스 파일 `input.cs`를 컴파일하고 `metad1.netmodule` 및 `metad2.netmodule`의 메타데이터를 추가하여 `out.exe`를 생성합니다.  
  
```  
csc /addmodule:metad1.netmodule;metad2.netmodule /out:out.exe input.cs  
```  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [다중 파일 어셈블리](../../../framework/app-domains/multifile-assemblies.md)   
 [방법: 다중 파일 어셈블리 빌드](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
