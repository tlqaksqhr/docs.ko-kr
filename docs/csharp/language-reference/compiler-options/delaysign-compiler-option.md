---
title: "-delaysign(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 74cd4caaa134f881297134867018346c323deeab
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="-delaysign-c-compiler-options"></a>-delaysign(C# 컴파일러 옵션)
이 옵션을 사용하면 나중에 디지털 시그니처를 추가할 수 있도록 컴파일러가 출력 파일에 공간을 예약합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-delaysign[ + | - ]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 완전히 서명된 어셈블리가 필요하면 **-delaysign-**를 사용합니다. 어셈블리에 공개 키만 배치하려면 **-delaysign+**를 사용합니다. 기본값은 **-delaysign-**입니다.  
  
## <a name="remarks"></a>설명  
 **-delaysign** 옵션은 [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) 또는 [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)와 함께 사용하지 않으면 효과가 없습니다.  
  
 완전히 서명된 어셈블리를 요청할 경우 컴파일러는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 개인 키로 해당 해시에 서명합니다. 결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다. 어셈블리 서명이 연기된 경우 컴파일러는 서명을 계산하거나 저장하지 않고 나중에 서명을 추가할 수 있도록 파일에 공간을 예약합니다.  
  
 예를 들어 **-delaysign+**를 사용하면 테스터를 통해 전역 캐시에 어셈블리를 넣을 수 있습니다. 테스트를 마친 후 [어셈블리 링커](../../../framework/tools/al-exe-assembly-linker.md) 유틸리티를 통해 어셈블리에 개인 키를 배치하여 어셈블리에 완전히 서명할 수 있습니다.  
  
 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) 및 [어셈블리 서명 지연](../../../framework/app-domains/delay-sign-assembly.md)을 참조하세요.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **서명만 연기** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)  
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
