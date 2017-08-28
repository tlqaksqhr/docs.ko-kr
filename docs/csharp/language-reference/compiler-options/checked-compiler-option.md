---
title: "-checked(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
caps.latest.revision: 20
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
ms.openlocfilehash: 63ba89ec42748ccea065bf0fd258fb559abca099
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="checked-c-compiler-options"></a>/checked(C# 컴파일러 옵션)
**/checked** 옵션은 데이터 형식 범위를 벗어나고 [checked](../../../csharp/language-reference/keywords/checked.md) 또는 [unchecked](../../../csharp/language-reference/keywords/unchecked.md) 키워드의 범위 내에 없는 값을 생성하는 정수 산술 문이 런타임 예외를 일으킬지 여부를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
/checked[+ | -]  
```  
  
## <a name="remarks"></a>주의  
 `checked` 또는 `unchecked` 키워드의 범위 내에 있는 정수 산술 문에는 **/checked** 옵션이 영향을 미치지 않습니다.  
  
 `checked` 또는 `unchecked` 키워드가 데이터 형식 범위를 벗어난 값을 생성하고 **/checked+**(**/checked**)가 컴파일에서 사용될 경우 해당 문은 런타임에 예외를 일으킵니다. **/checked-**가 컴파일에 사용될 경우 해당 문은 런타임에 예외를 일으키지 않습니다.  
  
 이 옵션의 기본값은 **/checked-**입니다. **/checked-** 사용에 대한 한 가지 시나리오는 큰 응용 프로그램을 빌드할 경우입니다. 자동화된 도구가 이러한 응용 프로그램을 빌드하는 데 사용되기도 하고 이 도구는 **/checked**를 자동으로 +로 설정할 수 있습니다. **/checked-**를 지정하여 도구의 전역 기본값을 재정의할 수 있습니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성** 페이지를 엽니다. 자세한 내용은 [프로젝트 디자이너, 빌드 페이지(C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)를 참조하세요.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **고급** 단추를 클릭합니다.  
  
4.  **산술 연산 오버플로/언더플로 확인** 속성을 수정합니다.  
  
 프로그래밍 방식으로 이 컴파일러 옵션에 액세스하려면 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 명령은 `t2.cs`를 컴파일합니다. 명령에서 `/checked`를 사용하면 `checked` 또는 `unchecked` 키워드의 범위에 없고 데이터 형식 범위를 벗어난 값을 생성하는 파일의 정수 산술 문이 런타임에 예외를 일으키도록 지정합니다.  
  
```console  
csc t2.cs /checked  
```  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)   
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)   
 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)

