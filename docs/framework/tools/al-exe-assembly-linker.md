---
title: "Al.exe(어셈블리 링커) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Al.exe"
  - "어셈블리 링커"
  - "모듈, 어셈블리 링커"
  - "어셈블리 매니페스트, 어셈블리 링커"
ms.assetid: b5382965-0053-47cf-b92f-862860275a01
caps.latest.revision: 37
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 37
---
# Al.exe(어셈블리 링커)
어셈블리 링커는 모듈 또는 리소스 파일인 하나 이상의 파일에서 어셈블리 매니페스트가 있는 파일을 생성합니다. 모듈이란 어셈블리 매니페스트가 없는 IL(Intermediate Language) 파일입니다.  
  
> [!NOTE]
>  어셈블리가 Windows Vista 컴퓨터에서 가상화되지 않게 하려면 요청되는 실행 수준을 지정하는 Win32 매니페스트가 어셈블리에 포함되어야 합니다. 명령줄에서 al.exe를 직접 사용할 때는 매니페스트를 Win32 리소스 파일에 포함할 수도 있고 mt.exe를 사용하여 빌드 프로세스의 이후 단계에서 매니페스트를 추가할 수도 있습니다. [!INCLUDE[vs_orcas_long](../../../includes/vs-orcas-long-md.md)]부터 C# 및 Visual Basic 컴파일러가 모두 win32 매니페스트를 어셈블리에 자동으로 포함시킵니다. 자세한 내용은 참조 [/win32manifest (C# 컴파일러 옵션)](../Topic/-win32manifest%20\(C%23%20Compiler%20Options\).md)합니다.  
  
 이 도구는 자동으로 Visual Studio와 함께 설치됩니다. 이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다. 자세한 내용은 참조 [명령 프롬프트가](../../../docs/framework/tools/developer-command-prompt-for-vs.md)합니다.  
  
 명령 프롬프트에 다음을 입력합니다.  
  
## <a name="syntax"></a>구문  
  
```  
al sources options  
```  
  
#### <a name="parameters"></a>매개 변수  
 다음 `sources` 중에서 하나 이상 지정할 수 있습니다.  
  
|소스|설명|  
|------------|-----------------|  
|`file`[,`target`]|`file`(모듈)의 내용을 `target`이 지정하는 파일 이름에 복사합니다. 복사한 후 Al.exe가 `target`을 어셈블리로 컴파일합니다.|  
|**/embed**[`resource`]`:``file`[,`name`[,`private`]]|`file`이 지정하는 리소스를 어셈블리 매니페스트가 포함된 이미지에 포함시킵니다. Al.exe는 `file`의 내용을 이식 가능한 실행 파일(PE) 이미지에 복사합니다.<br /><br /> `name` 매개 변수는 리소스의 내부 식별자입니다. 기본적으로 리소스는 어셈블리에서 공용입니다. 즉, 다른 어셈블리가 볼 수 있습니다. `private`를 지정하면 다른 어셈블리에서 리소스를 볼 수 없습니다.<br /><br /> 경우 `file` .NET Framework 리소스 파일인, 예를 들어에서 만든는 [리소스 파일 생성기 (Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 또는 개발 환경에서 액세스할 수의 멤버와는 <xref:System.Resources>합니다. 자세한 내용은 참조 <xref:System.Resources.ResourceManager>합니다. 다른 모든 리소스를 사용 하 여는 `GetManifestResource`* 메서드는 <xref:System.Reflection.Assembly> 런타임에 리소스에 액세스할 수 있습니다.<br /><br /> 리소스 파일만 Al.exe에 전달되는 경우에는 출력 파일이 위성 리소스 어셈블리입니다.|  
|**/link**[`resource`]:`file`[,`name`[,`target`[,`private`]]]|리소스 파일을 어셈블리에 링크합니다. `file`이 지정하는 리소스가 어셈블리의 일부가 되고 파일은 복사되지 않습니다. `file` 매개 변수는 어떠한 파일 형식도 될 수 있습니다. 예를 들어, 네이티브 DLL을 `file` 매개 변수로 지정할 수 있습니다. 이렇게 하면 네이티브 DLL이 어셈블리의 일부가 되므로 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있습니다. 사용 하 여이 수행할 수는 **/linkresource** 컴파일러 옵션입니다. 자세한 내용은 참조 [/linkresource (C# 컴파일러 옵션)](../Topic/-linkresource%20\(C%23%20Compiler%20Options\).md)합니다.<br /><br /> `name` 매개 변수는 리소스에 대 한 내부 식별자입니다. `target`매개 변수는 Al.exe 복사 경로 파일 이름을 지정 된 `file` *합니다.* 복사한 후 Al.exe가 `target`을 어셈블리로 컴파일합니다. 기본적으로 리소스는 어셈블리에서 공용입니다. 즉, 다른 어셈블리가 볼 수 있습니다. `private`를 지정하면 다른 어셈블리에서 리소스를 볼 수 없습니다.<br /><br /> 경우 `file` 만들어진,.NET Framework 리소스 파일은 예를 들어 리소스 파일 생성기 (Resgen.exe) 나 개발 환경에서 액세스할 수 있습니다의 멤버와는 <xref:System.Resources> 네임 스페이스입니다. 자세한 내용은 참조 <xref:System.Resources.ResourceManager>합니다. 사용 하 여 다른 모든 리소스는 `GetManifestResource` * 메서드는 <xref:System.Reflection.Assembly> 런타임에 리소스에 액세스 하는 클래스입니다.<br /><br /> 리소스 파일만 Al.exe에 전달되는 경우에는 출력 파일이 위성 리소스 어셈블리입니다.|  
  
 다음을 지정할 수 `options`; 지정 해야 **/출력**합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**/algid**:`id`|어셈블리 매니페스트가 포함된 파일을 제외하고 다중 파일 어셈블리에 있는 모든 파일을 해시하는 알고리즘을 지정합니다. 기본 알고리즘은 CALG_SHA1입니다. 다른 알고리즘에 대해서는 Platform SDK 설명서의 ALG_ID를 참조하세요. .NET Framework의 첫 릴리스에서는 CALG_SHA1과 CALG_MD5만 유효합니다.<br /><br /> 해시 값은 어셈블리 매니페스트의 파일 테이블에 저장됩니다. 설치 및 로드할 때 어셈블리의 파일을 해시와 비교하여 확인합니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyAlgorithmIdAttribute>) 모든 모듈에 대 한 소스 코드에 있습니다.|  
|**/base**[`address`]:`addr`|런타임에 DLL이 사용자의 컴퓨터에 로드되는 주소를 지정합니다. 운영 체제가 프로세스 공간에서 DLL을 재배치하게 하지 않고 DLL의 기본 주소를 직접 지정하면 응용 프로그램의 로드 속도가 빨라집니다.|  
|**/bugreport**:`filename`|버그를 보고하기 위한 정보가 포함된 파일(`filename`)을 만듭니다.|  
|**/comp**[`any`]:`text`|어셈블리의 Company 필드에 대한 문자열을 지정합니다. `text`에 공백이 있으면 문자열을 큰따옴표(" ")로 묶습니다. 이 문자열은 어셈블리의 사용자 지정 속성이며 리플렉션과 함께 볼 수 있습니다.<br /><br /> 지정 하지 않으면 **/win32res**, `text` 파일 탐색기에 표시 되는 `Company` 파일에 대 한 속성입니다. 지정 하는 경우 **/win32res**,으로 지정된 된 리소스 파일에서 회사 정보 표시는 `Company` 파일 탐색기의 속성입니다.<br /><br /> 텍스트가 빈 문자열("")이면 Win32 `Company` 리소스가 단일 공백으로 표시됩니다.<br /><br /> 지정 하는 경우 **/win32res**, **/회사** Win32 리소스 정보에 영향을 주지 것입니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyCompanyAttribute>) MSIL 모듈의 소스 코드에서.|  
|**/config**[`uration`]:`text`|어셈블리의 Configuration 필드에 대한 문자열을 지정합니다. `text`에 공백이 있으면 문자열을 큰따옴표(" ")로 묶습니다. 이 문자열은 어셈블리의 사용자 지정 속성이며 리플렉션과 함께 볼 수 있습니다.<br /><br /> 텍스트가 빈 문자열이면 Win32 Configuration 리소스가 단일 공백으로 표시됩니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyConfigurationAttribute>) MSIL 모듈의 소스 코드에서.|  
|**/copy**[`right`]:`text`|어셈블리의 Copyright 필드에 대한 문자열을 지정합니다. `text`에 공백이 있으면 문자열을 큰따옴표(" ")로 묶습니다. 이 문자열은 어셈블리의 사용자 지정 속성이며 리플렉션과 함께 볼 수 있습니다.<br /><br /> 지정 하지 않으면 **/win32res**, **copyright/** 저작권 Win32 리소스 파일 탐색기에 나타납니다.<br /><br /> 텍스트가 빈 문자열이면 Win32 Copyright 리소스가 단일 공백으로 표시됩니다.<br /><br /> 지정 하는 경우 **/win32res**, **copyright/** Win32 리소스 정보에 영향을 주지 것입니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyCopyrightAttribute>) MSIL 모듈의 소스 코드에서.|  
|**/c**[**ulture**]:`text`|어셈블리에 연결할 문화권 문자열을 지정합니다. "Tags for the Identification of Languages"라는 제목의 인터넷 RFC(Requests for Comments) 문서 1766에서 정의하는 값이 문화권의 유효한 값입니다.<br /><br /> `text`에 공백이 있으면 문자열을 큰따옴표(" ")로 묶습니다. 기본 문화권 문자열은 없습니다. 이 문자열을 리플렉션과 함께 볼 수 있습니다.<br /><br /> 유효한에 대 한 내용은 `text` 문자열 참조는 <xref:System.Globalization.CultureInfo>합니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyCultureAttribute>) MSIL 모듈의 소스 코드에서.|  
|**/delay**[`sign`][`+&#124;-`]|어셈블리를 완전히 서명할지, 아니면 부분적으로 서명할지를 지정합니다. 사용 하 여 **/delaysign-** 어셈블리에 완전히 서명된 하려는 경우. 사용 하 여 **/delaysign+** 어셈블리의 공개 키를 포함 하려는 경우.<br /><br /> 완전히 서명된 어셈블리를 요청할 경우 Al.exe는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 공개 키로 해당 해시에 서명합니다. 결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다. 어셈블리 서명이 연기된 경우 Al.exe는 서명을 계산하거나 저장하지 않고 나중에 서명을 추가할 수 있도록 파일에 공간을 예약합니다.<br /><br /> 기본값은 **/delaysign-**합니다.<br /><br /> **/delaysign** 와 사용 하지 않는 경우 옵션은 효과가 없습니다 **/keyfile** 또는 **/keyname**합니다.<br /><br /> 예를 들어를 사용 하 여 **/delaysign+** 하면 테스터가 어셈블리를 전역 캐시에 넣을 수 있습니다. 테스트를 마친 후 어셈블리에 개인 키를 포함하여 어셈블리에 완전히 서명할 수 있습니다.<br /><br /> 참고:를 사용 하기 전에 [Gacutil.exe (전역 어셈블리 캐시 도구)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 서명이 연기 된 어셈블리를 전역 캐시에 배치 하기 위해 사용 하 여는 [Sn.exe (강력한 이름 도구)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 확인을 건너뛸에 대 한 어셈블리를 등록 합니다. 예를 들어, `Sn.exe –Vr delaySignedAssembly`을 입력합니다. 개발에서만 이 기능을 사용하세요.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyDelaySignAttribute>) MSIL 모듈의 소스 코드에서.|  
|**/descr**[**iption**]**:**`text`|에 대 한 문자열을 지정 된 <xref:System.Reflection.AssemblyDescriptionAttribute.Description%2A> 어셈블리의 합니다. `text`에 공백이 있으면 문자열을 큰따옴표(" ")로 묶습니다. 이 문자열은 어셈블리의 사용자 지정 속성이며 리플렉션과 함께 볼 수 있습니다.<br /><br /> 지정 하지 않으면 **/win32res**, **/description** win32 파일 탐색기에 나타납니다 **의견** 리소스입니다.<br /><br /> 텍스트가 빈 문자열이 면 Win32 경우 **의견** 리소스가 단일 공간으로 나타납니다.<br /><br /> 지정 하는 경우 **/win32res**, **/description** Win32 리소스 정보에 영향을 주지 것입니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyDescriptionAttribute.Description%2A>) MSIL 모듈의 소스 코드에서.|  
|**/e [vidence]:**`file`|어셈블리에 `file`을 Security.Evidence라는 리소스 이름으로 포함시킵니다.<br /><br /> 기본 리소스에는 Security.Evidence를 사용할 수 없습니다.|  
|**/fileversion:**`version`|에 대 한 문자열을 지정 된 **파일 버전** 어셈블리의 합니다. 이 문자열은 어셈블리의 사용자 지정 속성이며 리플렉션과 함께 볼 수 있습니다.<br /><br /> 지정 하지 않으면 **/win32res**, **/fileversion** win32 사용할 **파일 버전** 리소스입니다. 지정 하지 않으면 **/fileversion**, Win32 **파일 버전** Win32 리소스 채워집니다 **어셈블리 버전** 리소스입니다.<br /><br /> 경우 **/win32res** 지정 **/fileversion** Win32 리소스에는 영향을 주지 않습니다.<br /><br /> MSIL 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성(AssemblyFileVersionAttribute)으로 지정할 수도 있습니다.|  
|**/flags:**`flags`|어셈블리의 `Flags` 필드에 대한 값을 지정합니다. `flags`에 사용할 수 있는 값은 다음과 같습니다.<br /><br /> 0x0000<br /> 어셈블리가 side-by-side로 호환됩니다.<br /><br /> 0x0010<br /> 어셈블리는 같은 응용 프로그램 도메인에서 실행할 경우 다른 버전과 함께 실행할 수 없습니다.<br /><br /> 0x0020<br /> 어셈블리는 같은 프로세스에서 실행할 경우 다른 버전과 함께 실행할 수 없습니다.<br /><br /> 0x0030<br /> 같은 컴퓨터에서 실행되는 경우에는 어셈블리를 다른 버전과 함께 실행할 수 없습니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyFlagsAttribute>) MSIL 모듈의 소스 코드에서.|  
|**/fullpaths**|오류 메시지에 보고되는 파일에 대해 Al.exe가 절대 경로를 사용합니다.|  
|**/help**|이 도구의 명령 구문 및 옵션을 표시합니다.|  
|**/keyf [ile]:**`filename`|어셈블리에 서명하기 위한 키 쌍 또는 공개 키를 포함하는 파일(`filename`)을 지정합니다. 컴파일러는 공개 키를 어셈블리 매니페스트에 삽입한 다음 개인 키를 사용하여 최종 어셈블리에 서명합니다. 참조는 [강력한 이름 도구 (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 키 파일을 생성 하 고 키 쌍을 키 컨테이너에 설치 하는 방법에 대 한 정보에 대 한 합니다.<br /><br /> 연기된 서명을 사용할 경우 이 파일에는 일반적으로 공개 키가 있으며 개인 키는 없습니다.<br /><br /> 키 쌍의 공개 키 정보는 어셈블리의 .publickey 필드에 나타납니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyKeyFileAttribute>) MSIL 모듈의 소스 코드에서.<br /><br /> 모두 **/keyfile** 및 **/keyname** 동일한 컴파일에서 Al.exe는 첫 번째 시도와 지정 된 컨테이너 (명령줄 옵션이 나 사용자 지정 특성)을 지정 된 **/keyname**합니다. 이 시도에 성공하면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다. Al.exe는 키 컨테이너를 찾지 못하면 지정 된 파일을 찾으려고 합니다 **/keyfile**합니다. 시도 성공 하면 어셈블리 키 파일의 정보로 서명 되 고 키 정보는 키 컨테이너에 설치 됩니다 (-i와 비슷합니다 옵션 [Sn.exe](../../../docs/framework/tools/sn-exe-strong-name-tool.md)) 하는 다음에 컴파일할은 **/keyname** 옵션이 유효 해 집니다.|  
|**/keyn \ [이름]:**`text`|키 쌍을 보관하는 컨테이너를 지정합니다. 어셈블리 매니페스트에 공개 키를 삽입하여 어셈블리에 서명(강력한 이름을 부여)합니다. 그런 다음 Al.exe가 개인 키를 사용하여 최종 어셈블리에 서명합니다.<br /><br /> Sn.exe를 사용하여 키 쌍을 생성합니다.<br /><br /> 어셈블리의 .publickey 필드에 키 정보가 나타납니다.<br /><br /> `text`에 공백이 있으면 큰따옴표(" ")로 묶습니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyKeyNameAttribute>) MSIL 모듈의 소스 코드에서.|  
|**/main:**`method`|모듈을 실행 파일로 변환할 때 진입점으로 사용할 메서드의 정규화된 이름(`class`.`method`)을 지정합니다.|  
|**/nologo**|Al.exe를 실행할 때 명령줄에 표시되는 배너 또는 로고를 표시하지 않습니다.|  
|**/out:**`filename`|Al.exe가 생성한 파일의 이름을 지정합니다. 필수 옵션입니다.|  
|**/platform**:`text`|이 코드를 실행할 수 있는 플랫폼은 x86, Itanium, x64, anycpu(기본값) 또는 anycpu32bitpreferred로 제한됩니다.|  
|**[uct] prod /:**`text`|에 대 한 문자열을 지정 된 **제품** 어셈블리의 합니다. `text`에 공백이 있으면 문자열을 큰따옴표(" ")로 묶습니다. 이 문자열은 어셈블리의 사용자 지정 속성이며 리플렉션과 함께 볼 수 있습니다.<br /><br /> 지정 하지 않으면 **/win32res**, **/product** win32 파일 탐색기에 나타납니다 **제품 이름** 리소스입니다.<br /><br /> 텍스트가 빈 문자열이 면 Win32 경우 **제품 이름** 리소스가 단일 공간으로 나타납니다.<br /><br /> 지정 하는 경우 **/win32res**, **/product** Win32 리소스 정보에 영향을 주지 것입니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyProductAttribute>) MSIL 모듈의 소스 코드에서.|  
|**/productv [및 속성 버전]:**`text`|에 대 한 문자열을 지정 된 **제품 버전** 어셈블리의 합니다. `text`에 공백이 있으면 문자열을 큰따옴표(" ")로 묶습니다. 이 문자열은 어셈블리의 사용자 지정 속성이며 리플렉션과 함께 볼 수 있습니다.<br /><br /> 지정 하지 않으면 **/win32res**, **/productversion** win32 사용할 **제품 버전** 리소스입니다. 지정 하지 않으면 **/productversion**, Win32 **제품 버전** Win32 리소스 채워집니다 **파일 버전** 리소스입니다.<br /><br /> 지정 하는 경우 **/win32res**, **/productversion** Win32 리소스 정보에 영향을 주지 것입니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyInformationalVersionAttribute>) MSIL 모듈의 소스 코드에서.|  
|**[arget] /t: lib [rary] | exe | win [exe]**|출력 파일의 형식을 lib[rary](코드 라이브러리), exe(콘솔 응용 프로그램) 또는 win[exe](Windows 기반 응용 프로그램)으로 지정합니다. 기본값은 lib[rary]입니다.|  
|**/template:**`filename`|culture 필드를 제외한 모든 어셈블리 메타데이터를 상속받을 상위 어셈블리, `filename`을 지정합니다.<br /><br /> 사용 하 여 만든 어셈블리 **/template** 어셈블리는 위성 어셈블리입니다.|  
|**/ t:**`text`|에 대 한 문자열을 지정 된 **제목** 어셈블리의 합니다. `text`에 공백이 있으면 문자열을 큰따옴표(" ")로 묶습니다. 이 문자열은 어셈블리의 사용자 지정 속성이며 리플렉션과 함께 볼 수 있습니다.<br /><br /> 지정 하지 않으면 **/win32res**, **/t** win32 파일 탐색기에 나타납니다 **설명** 셸에서 응용 프로그램의 표시 이름으로 사용 되는 리소스입니다. 에 표시는 **Open With** 지원 응용 프로그램이 여럿 파일 유형에 대 한 바로 가기 메뉴의 하위 메뉴입니다.<br /><br /> 텍스트가 빈 문자열이 면 Win32 경우 **설명** 리소스가 단일 공간으로 나타납니다.<br /><br /> 지정 하는 경우 **/win32res**, **/t** Win32 리소스 정보에 영향을 주지 것입니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyTitleAttribute>) MSIL 모듈의 소스 코드에서.|  
|**[표시] 거래 /:**`text`|에 대 한 문자열을 지정 된 **상표** 어셈블리의 합니다. `text`에 공백이 있으면 문자열을 큰따옴표(" ")로 묶습니다. 이 문자열은 어셈블리의 사용자 지정 속성이며 리플렉션과 함께 볼 수 있습니다.<br /><br /> 지정 하지 않으면 **/win32res**, **상표/** win32 파일 탐색기에 나타납니다 **상표** 리소스입니다.<br /><br /> 텍스트가 빈 문자열이 면 Win32 경우 **상표** 리소스가 단일 공간으로 나타납니다.<br /><br /> 지정 하는 경우 **/win32res**, **상표/** Win32 리소스 정보에 영향을 주지 것입니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyTrademarkAttribute>) MSIL 모듈의 소스 코드에서.|  
|**/v [및 속성 버전]:**`version`|이 어셈블리의 버전 정보를 지정합니다. 버전 문자열의 형식은 `major`.`minor`.`build`.`revision`입니다. 기본값은 0입니다.<br /><br /> 지정 않으면 **/version**를 지정 해야 `major`합니다. 지정 하는 경우 `major` 및 `minor`, 별표를 지정할 수 있습니다 (\*)에 대 한 `build`합니다. 이 경우 `build`는 현지 시간 2000년 1월 1일부터 경과된 일수와 일치하며, `revision`은 현재 날짜, 현지 시간, 자정부터 경과된 초 수를 2로 나눈 값과 일치합니다.<br /><br /> `major`, `minor` 및 `build`를 지정하면 `revision`에 대해 별표를 지정할 수 있습니다. 이 경우 `revision`은 현재 날짜, 현지 시간, 자정부터 경과된 초 수를 2로 나눈 값과 일치합니다.<br /><br /> 유효한 버전 문자열을 요약하면 다음과 같습니다.<br /><br /> X<br /><br /> X.X<br /><br /> X.X.\*<br /><br /> X.X.X<br /><br /> X.X.X.\*<br /><br /> X.X.X.X<br /><br /> 여기서 X는 65535를 제외한 부호 없는 short 상수(0-65534)입니다.<br /><br /> 지정 하지 않으면 **/win32res**, **/version** win32 사용할 **어셈블리 버전** 리소스입니다.<br /><br /> 지정 하지 않으면 **/win32res**, **/productversion**, 및 **/fileversion**, **/version** 에 사용할는 **어셈블리 버전**, 파일 버전 및 **제품 버전** Win32 리소스입니다.<br /><br /> 지정 하는 경우 **/win32res**, **/version** Win32 리소스 정보에 영향을 주지 것입니다.<br /><br /> 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyVersionAttribute>) MSIL 모듈의 소스 코드에서.|  
|**/win32icon:**`filename`|.ico 파일을 어셈블리에 삽입합니다. .ico 파일을 사용하면 파일 탐색기에서 출력 파일을 원하는 모양으로 나타납니다.|  
|**/win32res:**`filename`|Win32 리소스(.res 파일)를 출력 파일에 삽입합니다. Win32 리소스 파일은 리소스 컴파일러를 사용하여 만듭니다. 리소스 컴파일러는 Visual C++ 프로그램을 컴파일할 때 실행되며 .rc 파일에서 .res 파일이 만들어집니다.|  
|`@filename`|Al.exe 명령을 포함하는 지시 파일을 지정합니다.<br /><br /> 지시 파일의 명령은 한 줄에 하나씩 나타나거나 하나 이상의 공백으로 분리되어 같은 줄에 나타날 수 있습니다.|  
|**/?**|이 도구의 명령 구문 및 옵션을 표시합니다.|  
  
## <a name="remarks"></a>설명  
 모든 Visual Studio 컴파일러는 어셈블리를 만듭니다. 그러나 모듈(매니페스트 없는 메타데이터)이 하나 이상 있으면 Al.exe를 사용하여 별도의 파일에 매니페스트가 있는 어셈블리를 만들 수 있습니다.  
  
 캐시에 어셈블리를 설치 하려면, 캐시에서 어셈블리를 제거 하거나 캐시의 내용을 나열, 사용 된 [전역 어셈블리 캐시 도구 (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)합니다.  
  
## <a name="errors-and-warnings"></a>오류 및 경고  
 다음 표에서는 Al.exe에 의해 생성된 오류를 보여 줍니다.  
  
|오류|설명|  
|-----------|-----------------|  
|al1001|내부 컴파일러 오류<br /><br /> Al.exe가 예기치 않은 구문을 분석할 수 없어 실패하는지 여부를 확인합니다. 그런 다음 Microsoft 기술 지원 서비스에 문의하세요.|  
|al1002|메모리 부족<br /><br /> Al.exe가 메모리 부족으로 중지되었습니다. 사용 가능한 메모리 양을 늘립니다.|  
|al1003|'option' 컴파일러 옵션 다음에는 인수가 와야 합니다.<br /><br /> Al.exe에서 명령줄 옵션에 인수가 전달될 것으로 예상했습니다. 예를 들어 지정 하는 경우 **/algid:**, 알고리즘 식별자를 전달 해야 합니다.|  
|al1004|예기치 않은 공용 언어 런타임 초기화 오류 - 'reason'<br /><br /> Al.exe에서 지정된 이유로 Visual Studio 또는 공용 언어 런타임 설치 오류를 보고했습니다.|  
|al1005|'file' 파일이 너무 커서 열 수 없습니다.<br /><br /> Al.exe에서 여는 모든 파일은 4GB(기가바이트)보다 작아야 합니다.|  
|al1006|'file' 지시 파일이 이미 포함되었습니다.<br /><br /> 동일한 지시 파일이 명령줄에서 두 번 이상 지정되었습니다(`@file`). 지시 파일은 한 번만 포함될 수 있습니다.|  
|al1007|'file' 지시 파일을 여는 동안 오류가 발생했습니다. 'reason'<br /><br /> Al.exe에서 지정된 이유로 지정된 지시 파일을 열 수 없습니다.|  
|al1008|'option' 명령줄 옵션에 대한 파일 사양이 없습니다.<br /><br /> Al.exe에서 명령줄 옵션에 파일이 전달될 것으로 예상했습니다. 예를 들어 지정 하는 경우는 **/출력** 옵션을 파일을 지정 해야 합니다.|  
|al1009|'file'을 쓰기용으로 열 수 없습니다.<br /><br /> Al.exe에서 출력 어셈블리 파일과 같은 파일에 쓸 수 없습니다. 디스크가 꽉 찼거나, 파일이 읽기 전용이거나, 파일에 대한 권한이 없을 수 있습니다.|  
|al1010|명령줄 구문 오류: 'option' 옵션에 대한 ':text'가 없습니다.<br /><br /> Al.exe에서 명령줄 옵션에 인수가 전달될 것으로 예상했습니다. 예를 들어 지정 하는 경우는 **/t** 옵션을 문자열로 전달 해야 합니다.|  
|al1011|'file' 파일은 실행 파일이며 텍스트 파일로 열 수 없습니다.<br /><br /> 텍스트 파일이 필요한 위치에 이진 파일이 지정되었습니다. 예를 들어 명령줄에서 이진 파일이 지시 파일로 전달되면 이 오류가 발생합니다.|  
|al1012|'value'가 'option' 옵션에 유효한 설정이 아닙니다.<br /><br /> 예기치 않은 값이 명령줄 옵션에 전달되었습니다. 에 잘못 된 값을 지정 하는 경우이 오류가 발생 하는 예를 들어는 **/대상** 옵션입니다.|  
|al1013|인식할 수 없는 명령줄 옵션: 'option'<br /><br /> 잘못된 명령줄 옵션을 지정했습니다.|  
|al1014|예기치 않은 초기화 오류 - 'reason'<br /><br /> Al.exe에서 COM 초기화 오류를 발견했습니다. 이 오류는 메모리 부족으로 발생할 수도 있지만 시스템 DLL 파일 때문일 가능성이 더 큽니다. Microsoft Visual Studio와 같은 자동화 인식 또는 COM 인식 프로그램을 실행하면 유사한 오류가 표시됩니다.<br /><br /> 운영 체제를 다시 설치합니다.|  
|al1015|'alinkui.dll' 메시지 파일을 찾을 수 없습니다.<br /><br /> Al.exe를 사용하려면 Alinkui.dll이 필요합니다. 이 파일이 경로에 있는지 확인합니다. 필요한 경우 제품 CD에서 복사합니다.|  
|al1016|유효한 입력 파일을 지정하지 않았습니다.<br /><br /> Al.exe를 사용하려면 어셈블리 정보가 없는 입력 파일이 하나 이상 필요합니다.|  
|al1017|대상 파일 이름을 지정하지 않았습니다.<br /><br /> 필수 **/출력** 누락 된 대상 파일 이름을 지정 하는 옵션입니다.|  
|al1018|‘file’ 필수 파일을 로드할 수 없습니다.<br /><br /> 특정 DLL 파일을 로드할 수 없습니다. Visual Studio 또는 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]를 다시 설치합니다.|  
|al1019|어셈블리를 만드는 동안 메타데이터 오류 발생 - reason<br /><br /> 지정된 이유로 어셈블리 생성이 중단되었습니다. 예를 들어이 오류가 발생 하는 경우 사용 하 여 지정한 파일은 **/win32res** 옵션을 찾을 수 없습니다.|  
|al1020|포함된 어셈블리 'file'을 무시합니다.<br /><br /> 어셈블리를 포함하는 입력 파일을 지정했습니다. Al.exe 입력 파일은 어셈블리를 포함할 수 없습니다.|  
|al1021|'setting': 이전 설정 재정의<br /><br /> 모듈에 사용자 지정 특성을 통해 할당된 특정 설정 값이 있었습니다. 이 값이 Al.exe 명령줄 옵션을 사용하여 전달된 값으로 대체되었습니다.|  
|al1022|포함된 리소스 'file'을 읽는 동안 오류 발생 - reason<br /><br /> Al.exe에 전달 된 파일을 읽을 수 없습니다는 **/embedresource** 지정된 된 원인에 대 한 옵션입니다.|  
|al1023|리소스 'file'을 포함하는 동안 오류 발생 - reason<br /><br /> 운영 체제에서 지정된 이유로 어셈블리에 리소스 파일을 포함할 수 없습니다.|  
|al1025|ComType 레코드 'record'가 잘못 된 파일 레코드 'record'를 가리킵니다.<br /><br /> 입력 모듈의 메타데이터가 잘못되었습니다. 모듈을 생성한 도구를 수정해야 합니다.|  
|al1026|지정된 ‘version’ 버전이 잘못되었습니다.<br /><br /> 정보에 대 한 참조는 **/version** 유효한 형식에 대 한 옵션입니다.|  
|al1028|'file' 키 파일에 서명에 필요한 개인 키가 없습니다.<br /><br /> 에 전달 된 공개 키만 포함 된 키 파일은 **/keyfile** 옵션입니다. 사용 하 여 [강력한 이름 도구 (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 다음 명령에 표시 된 것 처럼 두 공용 및 개인 키를 가진 파일을 생성 하 합니다.<br /><br /> `sn -k keypair.snk.`|  
|al1029|키 컨테이너 이름 ‘container’가 없습니다.<br /><br /> 에 전달 된 값은 **/keyname** 옵션은 유효한 컨테이너가 없습니다. 사용 하는 [강력한 이름 도구 (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 컨테이너를 만들어야 합니다.|  
|al1030|암호화 서비스가 제대로 설치되지 않았거나 적절한 키 공급자가 없습니다.<br /><br /> 운영 체제를 다시 설치하거나, 키를 만드는 데 사용되는 일부 암호화 유틸리티를 설치해야 할 수 있습니다.|  
|al1031|'file' 아이콘을 읽는 동안 오류 발생 - reason<br /><br /> Al.exe에 전달 된 파일을 읽을 수 없습니다는 **/win32icon** 지정된 된 원인에 대 한 옵션|  
|al1032|'file'에 대한 리소스를 생성하는 동안 오류 발생 - reason<br /><br /> 디스크 공간 부족 또는 일부 다른 오류로 인해 Al.exe에서 파일을 만들 수 없습니다. 지정 하는 경우이 오류가 발생 된 **/win32icon** (.ico 파일 생성) 옵션을 선택 하거나 지정 하지 않으면는 **/win32res** 옵션 (리소스 정보가 포함 된 파일을 생성 함).<br /><br /> 파일 생성 문제를 해결할 수 없는 경우 사용 하 여 **/win32res**, 파일 버전을 포함 하거나 비트맵 (아이콘) 정보는 지정 합니다.|  
|al1033|어셈블리 사용자 지정 특성 'attribute'가 서로 다른 값으로 여러 번 지정되었습니다.<br /><br /> Al.exe에 대한 입력으로 지정된 소스 모듈의 동일한 사용자 지정 특성 발생 두 개에 서로 다른 값이 전달되었습니다.|  
|al1034|'file' 어셈블리를 복사하거나 이름을 바꿀 수 없습니다.<br /><br /> 입력 파일을 지정하고 복사할 수 있게 해주는 Al.exe 구문을 사용하는 동안 이름 충돌이 발생하여 컴파일러가 중지되었습니다. 예를 들어 이 오류는 `input.dll,somename.dll /out:somename.dll`을 지정하는 경우 발생합니다.|  
|al1035|라이브러리는 진입점을 포함할 수 없습니다.<br /><br /> 모두를 지정할 수 없습니다는 **/target:lib** 옵션 (기본값) 및 **/main** 옵션입니다.|  
|al1036|실행 가능한 응용 프로그램에는 진입점이 필요합니다.<br /><br /> 사용 하는 경우는 **/target: exe** 또는 **/target:win** 옵션을 지정 해야는 **/main** 옵션입니다.|  
|al1037|'main' 진입점 메서드를 찾을 수 없습니다.<br /><br /> Al.exe를 찾을 수 없습니다는 `Main` 메서드에 지정 된 위치에는 **/main** 옵션입니다.|  
|al1039|전역 어셈블리 캐시 관리자 초기화 실패 - reason<br /><br /> Visual Studio 또는 [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]를 다시 설치합니다.|  
|al1040|캐시에 어셈블리를 설치하지 못했습니다. reason<br /><br /> 서명된 어셈블리만 캐시에 설치할 수 있습니다. 참조 [전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md) 에 대 한 자세한 내용은 합니다.|  
|al1041|'method': 서명 또는 표시 유형이 잘못되었거나 제네릭이기 때문에 진입점이 될 수 없습니다.<br /><br /> 으로 메서드가 지정 된는 **/main** 옵션을 하지만 해당 메서드가 정적이 아니거나, 반환 하지 않는 `int` 또는 `void`, 제네릭 이거나, 잘못 된 인수가 있습니다.|  
|al1042|'exe': EXE를 모듈로 추가할 수 없습니다.<br /><br /> 어셈블리가 없는 .exe 파일이 Al.exe에 대한 입력 파일로 지정되었습니다. Al.exe는 어셈블리가 없는 .dll 파일만 입력 파일로 사용할 수 있습니다.|  
|al1043|'name' 매니페스트 파일 이름은 모듈과 같을 수 없습니다.<br /><br /> 지정 된 이름은 **/출력** 옵션 Al.exe에 대 한 입력으로 지정 된 파일 이름 중 하나로 같을 수 없습니다.|  
|al1044|'file' 키 파일을 읽는 동안 오류 발생 - reason<br /><br /> 지정 된 파일을 열거나 읽는 동안 오류가 발생 했습니다. **/keyfile** 또는 <xref:System.Reflection.AssemblyKeyFileAttribute>합니다.|  
|al1045|‘file’ 파일 이름이 너무 길거나 잘못되었습니다.<br /><br /> 260자보다 긴 파일 이름이 Al.exe에 전달되었습니다. 더 적은 문자를 포함하거나 경로가 더 짧은 파일 이름을 선택하거나 파일 이름을 바꿉니다.|  
|al1046|'ID' 리소스 식별자가 이 어셈블리에서 이미 사용되었습니다.<br /><br /> 포함 또는 연결된 두 리소스에 동일한 식별자 또는 이름(두 번째 인수)이 있습니다. 충돌하는 리소스 중 하나를 제거하거나 이름을 바꿉니다.|  
|al1047|'file' 파일을 가져오는 동안 오류 발생 - reason<br /><br /> 지정된 이유로 모듈 파일을 열 수 없습니다.|  
|al1048|'assembly' 어셈블리의 'module' 모듈을 가져오는 동안 오류 발생 - reason<br /><br /> 다중 파일 어셈블리의 비매니페스트 파일을 열 때 오류가 발생했습니다. 이 오류는 Al.exe에서 직접 내보내지 않고 Al.exe를 사용하는 프로세스에 프로그래밍 방식으로 전달될 수 있습니다.|  
|al1049|2000년 1월 1일 이전 날짜에 대한 빌드 및 수정 버전 번호를 자동으로 생성할 수 없습니다.<br /><br /> 컴퓨터의 시스템 시계가 2000년 1월 1일 이전 날짜로 설정되었습니다.|  
|al1050|'old feature'를 사용하는 기능은 더 이상 지원되지 않습니다. 'new feature'를 대신 사용하세요.<br /><br /> 이전에 Al.exe에서 지원한 기능이 이제 사용되지 않습니다. 권장 기능을 대신 사용합니다.|  
|al1051|'attribute' 특성을 내보내는 동안 오류 발생 - 'reason'<br /><br /> 지정된 이유로 어셈블리 사용자 지정 특성이 Al.exe에서 처리되지 않았습니다.|  
|al1052|‘filename’ 파일은 어셈블리가 아닙니다.<br /><br /> 지정 된 파일 **/template** 어셈블리 메타 데이터를 포함 해야 합니다. 이 오류는 지정 하는 파일 나타냅니다 **/template** 어셈블리를 포함 하지 않았습니다.|  
|al1053|'옵션'에 대해 지정된 'version' 버전은 일반적인 'major.minor.build.revision' 형식이 아닙니다.<br /><br /> Al.exe에 잘못 된 형식의 버전 정보가 지정 된 검색의 **/fileversion** 또는 **/productversion** 옵션입니다.|  
|al1054|'옵션'에 대해 지정된 'version' 버전은 일반적인 'major.minor.build.revision' 형식이 아닙니다.<br /><br /> Al.exe에 잘못 된 형식의 버전 정보가 지정 된 검색의 <xref:System.Resources.SatelliteContractVersionAttribute>합니다.|  
|al1055|참조된 ‘filename’ 어셈블리에 강력한 이름이 없습니다.<br /><br /> 이 오류는 강력한 이름의 어셈블리를 빌드하고 강력한 이름이 없는 어셈블리를 참조하는 경우에 발생합니다. 이 해결 하려면 강력한 이름의 어셈블리를 다시 생성 하거나 sn.exe를 사용 하 여 어셈블리에 강력한 이름을 연결 (에 대 한 설명서를 참조 하십시오. [sn.exe](../../../docs/framework/tools/sn-exe-strong-name-tool.md)).<br /><br /> 일반적으로 이 오류는 Visual Studio IDE를 통해 C# 프로젝트에 COM 모듈 참조를 추가하는 경우와 같이 래퍼 어셈블리를 통해 COM 개체를 사용하는 경우에 발생합니다. 오류를 방지하려면 "래퍼 어셈블리 키 파일/이름" 프로젝트 속성에서 COM 래퍼 어셈블리에 대한 강력한 이름 키 파일을 지정할 수 있습니다.<br /><br /> Tlbimp 통해 래퍼 어셈블리를 만드는 경우 참조는 [tlbimp](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) 래퍼 어셈블리에 강력한 이름을 할당 하는 방법에 대 한 정보에 대 한 설명서입니다.<br /><br /> 어셈블리에 강력한 이름이 있는 경우 전역 어셈블리 캐시에 설치할 수 있습니다. 결과적으로, 참조된 어셈블리도 전역 어셈블리 캐시로 이동됩니다. 강력한 이름을 가진 어셈블리만 전역 어셈블리 캐시로 이동될 수 있습니다.|  
|al1056|참조된 'filename' 어셈블리는 지역화된 위성 어셈블리입니다.<br /><br /> 사용 하 여 생성 된 어셈블리는 <xref:System.Reflection.AssemblyCultureAttribute> 특성 만들기는 현재 어셈블리에서 참조 되었습니다. <xref:System.Reflection.AssemblyCultureAttribute> 특성 파일은 지역화 된 위성 어셈블리 이며 위성 어셈블리를 참조 하는 데 적합 하지 않음을 나타냅니다. 기본 부모 어셈블리를 대신 참조해야 합니다.|  
|al1057|실행 파일을 지역화할 수 없습니다. 문화권은 항상 비어 있어야 합니다.<br /><br /> 어셈블리를 사용 하 여 만들려는 **/target: exe** 하지만 **/문화권** 지정 되었습니다. .exe의 어셈블리는 Culture 필드에 정보를 포함할 수 없습니다.|  
|al1058|'file'은 어셈블리이며 모듈로 추가할 수 없습니다.<br /><br /> C + + 컴파일에서 **/assemblymodule** (링커 옵션)에 어셈블리를 포함 하는 파일이 전달 되었습니다.|  
|al1059|알 수 없는 오류(code)<br /><br /> Al.exe가 알 수 없는 오류 코드(`code`)를 받았습니다.<br /><br /> 가능한 해결 방법은 다음과 같습니다.<br /><br /> Visual Studio를 다시 설치합니다.<br /><br /> [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]를 다시 설치합니다.<br /><br /> 누락된 파일이 있는지 확인합니다.<br /><br /> 디스크 공간이 충분한지 확인합니다.<br /><br /> 메모리가 충분한지 확인합니다.<br /><br /> 파일에 액세스할 수 있는 다른 프로세스를 중지합니다.<br /><br /> 컴퓨터를 다시 부팅합니다.|  
|al1060|해시를 만드는 동안 암호화 오류 발생 - reason<br /><br /> 다중 파일 어셈블리에 대한 파일 해시를 만드는 동안 오류가 발생했습니다.|  
|al1061|'reason' 때문에 'option' 옵션을 설정할 수 없습니다.<br /><br /> 지정된 이유로 이 옵션에 대해 지정된 값이 잘못되었습니다.|  
|al1062|'module' 모듈이 여러 번 지정되었습니다. 한 번만 포함됩니다.<br /><br /> 이 경고는 동일한 소스, 입력 또는 모듈 파일이 명령줄에서 여러 번 지정될 때 생성됩니다. 파일 이름을 한 번만 지정해야 합니다.|  
|al1063|이 어셈블리의 여러 위치에서 'type' 공용 형식이 정의되었습니다. 'file1' 및 'file2'<br /><br /> 어셈블리의 둘 이상 모듈에서 동일한 형식이 발견되었습니다. 각 형식의 버전이 어셈블리에 하나씩만 포함될 수 있습니다.|  
|al1064|/bugreport 옵션을 여러 개 지정할 수 없습니다.<br /><br /> 하나의 **/bugreport** 옵션을 사용할 수 있습니다.|  
|al1065|‘File Name’ 파일 이름이 너무 길거나 잘못되었습니다.<br /><br /> 지정된 파일 이름이 허용되는 최대값보다 깁니다.|  
|al1066|'character' 문자는 명령줄 또는 지시 파일에서 사용할 수 없습니다.<br /><br /> 명령줄 또는 파일에서 잘못된 문자가 발견되었습니다.|  
|al1067|'filename'은 텍스트 파일이 아니라 이진 파일입니다.<br /><br /> 파일이 텍스트가 아니라 이진 형식입니다.|  
|al1068|'ModuleName' 모듈은 이 어셈블리에서 이미 정의되었습니다. 연결된 각 리소스 및 모듈에 고유한 파일 이름이 있어야 합니다.<br /><br /> 이 어셈블리에서 모듈이 두 번 이상 발생합니다.|  
|al1069|동일한 약식 파일 이름을 가진 긴 파일 이름이 이미 있을 경우 'filename' 약식 파일 이름을 만들 수 없습니다.<br /><br /> 현재 파일 이름의 약식 버전이 이미 존재합니다. 예를 들어 LongFileName.cs를 컴파일한 다음 LongFi~1.cs 이름으로 다시 컴파일하면 다음과 비슷한 컴파일러 오류가 발생합니다. 긴 이름을 가진 컴파일러 출력 파일이 삭제되었지만 유사한 링커 파일이 남아 있는 경우 이 오류가 발생할 수 있습니다.|  
|al1070|알 수 없는 어셈블리는 프로세서의 특정 모듈('Module Name')을 포함할 수 없습니다.<br /><br /> 사용 하 여 빌드하는 경우 **/platform:agnostic** (지정 하지 않으면 또는 **/platform**), 모듈을 추가 하려고 하면 오류가 생성 됩니다 (사용 하 여 **/addmodule**) 알 수 없는 합니다. 이는 ia64 obj에 i386 obj 파일을 연결하려는 것과 같습니다.<br /><br /> 특정 모듈의 기본 소스는 C++입니다. 사용 중인 경우 **/addmodule** c + + 모듈을 적절 한 지정할 빌드 스크립트를 수정 해야 **/platform** 설정 합니다.|  
|al1072|어셈블리 및 'Module Name' 모듈은 다른 프로세서를 대상으로 할 수 없습니다.<br /><br /> 결과를 단일 프로세서에서 실행해야 하므로 서로 다른 프로세서를 대상으로 하는 어셈블리와 모듈을 연결할 수 없습니다.|  
|al1073|참조된 ‘assembly’ 어셈블리가 다른 프로세서를 대상으로 합니다.<br /><br /> 결과를 단일 프로세서에서 실행해야 하므로 서로 다른 프로세서를 대상으로 하는 어셈블리를 연결할 수 없습니다.|  
|al1074|'File Name'에 저장된 'Module Name' 모듈 이름은 해당 파일 이름과 일치해야 합니다.<br /><br /> 이는 링커에 필요합니다. 이 문제를 해결하려면 두 이름이 일치하도록 만듭니다.|  
|al1075|서명 연기가 요청되었지만 키가 지정되지 않았습니다.<br /><br /> 어셈블리 서명이 연기된 경우 컴파일러는 서명을 계산하거나 저장하지 않고 나중에 서명을 추가할 수 있도록 파일에 공간을 예약합니다.<br /><br /> 예를 들어를 사용 하 여 **/delaysign+** 하면 테스터가 어셈블리를 전역 캐시에 넣을 수 있습니다. 테스트를 마친 후 어셈블리 링커 유틸리티를 통해 어셈블리에 개인 키를 추가하여 어셈블리에 완전히 서명할 수 있습니다.|  
|al1076|'type' 형식이 여러 어셈블리에 전달되었습니다. 'assembly' 및 'assembly'.<br /><br /> 각 형식을 하나의 어셈블리에만 전달할 수 있습니다.|  
|al1077|'type' public 형식이 'assembly'에서 정의되고 'assembly'로 전달됩니다.<br /><br /> 생성되는 어셈블리에 중복된 public 형식이 있습니다. 하나는 유효한 형식 정의이고 다른 하나는 형식 전달자입니다.|  
  
## <a name="example"></a>예제  
 다음 명령은 `t2a.exe` 모듈의 어셈블리를 사용하여 실행 파일 `t2.netmodule`를 만듭니다. 진입점은 `Main`의 `MyClass` 메서드입니다.  
  
```  
al t2.netmodule /target:exe /out:t2a.exe /main:MyClass.Main  
```  
  
## <a name="see-also"></a>참고 항목  
 [도구](../../../docs/framework/tools/index.md)   
 [Sn.exe (강력한 이름 도구)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [Gacutil.exe (전역 어셈블리 캐시 도구)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)   
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)