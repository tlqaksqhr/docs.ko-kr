---
title: "-keyfile(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fc80c1f6614cdfc8e2f56855d0a0315977316f4c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="-keyfile-c-compiler-options"></a>-keyfile(C# 컴파일러 옵션)
암호화 키를 포함하는 파일 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|----------|----------------|  
|`file`|강력한 이름 키를 포함하는 파일의 이름입니다.|  
  
## <a name="remarks"></a>설명  
 이 옵션을 사용하면 컴파일러는 지정된 파일의 공개 키를 어셈블리 매니페스트에 삽입한 다음 개인 키를 사용하여 최종 어셈블리에 서명합니다. 키 파일을 생성하려면 명령줄에 sn -k `file`을 입력합니다.  
  
 **-target:module**로 컴파일하는 경우 키 파일의 이름이 모듈에 저장되고, [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)을 사용하여 어셈블리를 컴파일할 때 생성되는 어셈블리에 통합됩니다.  
  
 [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)를 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다. 부분 서명된 어셈블리가 필요한 경우 [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)을 사용합니다.  
  
 동일한 컴파일에서 -keyfile 및 -keycontainer를 명령줄 옵션이나 사용자 지정 특성으로 둘 다 지정하면 컴파일러는 먼저 키 컨테이너를 찾습니다. 키 컨테이너를 찾으면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다. 컴파일러는 키 컨테이너를 찾지 못할 경우 -keyfile로 지정된 파일을 찾습니다. 해당 파일을 찾으면 키 파일의 정보를 사용하여 어셈블리가 서명되고, 키 정보가 키 컨테이너에 설치되므로(sn -i와 유사) 다음에 컴파일할 때 키 컨테이너가 유효해집니다.  
  
 키 파일에는 공개 키만 포함될 수 있습니다.  
  
 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) 및 [어셈블리 서명 지연](../../../framework/app-domains/delay-sign-assembly.md)을 참조하세요.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **서명** 속성 페이지를 클릭합니다.  
  
3.  **강력한 이름 키 파일 선택** 속성을 수정합니다.  
  
 프로그래밍 방식으로 <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>을 사용하여 이 컴파일러 옵션에 액세스할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)  
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
