---
title: "-keycontainer(C# 컴파일러 옵션) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /keycontainer
dev_langs:
- CSharp
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: 17
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
ms.openlocfilehash: 30b851a3e44c90582227beda7245a7c4b0d57b47
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="keycontainer-c-compiler-options"></a>/keycontainer(C# 컴파일러 옵션)
암호화 키 컨테이너의 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
/keycontainer:string  
```  
  
## <a name="arguments"></a>인수  
 `string`  
 강력한 이름 키 컨테이너의 이름입니다.  
  
## <a name="remarks"></a>설명  
 **/keycontainer** 옵션을 사용하면 컴파일러는 지정된 컨테이너의 공개 키를 어셈블리 매니페스트에 삽입하고 최종 어셈블리를 개인 키로 서명하여 공유할 수 있는 구성 요소를 만듭니다. 키 파일을 생성하려면 명령줄에 sn -k `file`을 입력합니다. sn -i는 컨테이너에 키 쌍을 설치합니다.  
  
 [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)로 컴파일하는 경우 키 파일의 이름이 모듈에 저장되고, [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)을 사용하여 이 모듈을 어셈블리로 컴파일할 때 어셈블리에 통합됩니다.  
  
 MSIL(Microsoft Intermediate Language) 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성(<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>)으로 지정할 수도 있습니다.  
  
 [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)을 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다. 공개 키를 어셈블리 매니페스트에 추가하지만 테스트가 완료될 때까지 어셈블리 서명을 지연하려는 경우 [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)을 사용합니다.  
  
 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](https://msdn.microsoft.com/library/xwb8f617) 및 [어셈블리 서명 지연](../../../framework/app-domains/delay-sign-assembly.md)을 참조하세요.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  이 컴파일러 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다.  
  
 프로그래밍 방식으로 <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>을 사용하여 이 컴파일러 옵션에 액세스할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
