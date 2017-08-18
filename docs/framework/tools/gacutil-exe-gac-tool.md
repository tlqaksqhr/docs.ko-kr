---
title: "Gacutil.exe(전역 어셈블리 캐시 도구)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- global assembly cache, manipulating contents
- GAC (global assembly cache), Gacutil.exe
- Gacutil.exe
- GAC (global assembly cache), viewing contents
- installing assemblies into global assembly cache
- removing assemblies from global assembly cache
- list of assemblies in global assembly cache
- cache [.NET Framework], global assembly cache
- GAC (global assembly cache), manipulating contents
- global assembly cache, Gacutil.exe
- Global Assembly Cache tool
ms.assetid: 4c7be9c8-72ae-481f-a01c-1a4716806e99
caps.latest.revision: 17
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a42ef6cc2a1418c5071f94f4c8a7497a8701a73a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="gacutilexe-global-assembly-cache-tool"></a>Gacutil.exe(전역 어셈블리 캐시 도구)
전역 어셈블리 캐시 도구를 사용하면 전역 어셈블리 캐시와 다운로드 캐시의 내용을 보고 조작할 수 있습니다.  
  
 이 도구는 자동으로 Visual Studio와 함께 설치됩니다. 이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다. 자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.  
  
 명령 프롬프트에 다음을 입력합니다.  
  
## <a name="syntax"></a>구문  
  
```  
gacutil [options] [assemblyName | assemblyPath | assemblyListFile]  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|인수|설명|  
|--------------|-----------------|  
|*assemblyName*|어셈블리의 이름입니다. `myAssembly`와 같이 부분적인 어셈블리 이름이나 `myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5`와 같이 완전한 어셈블리 이름을 제공할 수 있습니다.|  
|*assemblyPath*|어셈블리 매니페스트가 들어 있는 파일의 이름입니다.|  
|*assemblyListFile*|설치 또는 제거할 어셈블리를 나열하는 ANSI 텍스트 파일의 경로입니다. 텍스트 파일을 사용하여 어셈블리를 설치하려면 각 어셈블리 경로를 해당 파일에서 별도의 줄에 지정하십시오. 이 도구에서는 각 파일의 경로를 *assemblyListFile*의 위치를 기준으로 하는 상대 경로로 해석합니다. 텍스트 파일을 사용하여 어셈블리를 제거하려면 각 어셈블리의 정규화된 어셈블리 이름을 해당 파일에서 별도의 줄에 지정하십시오. 자세한 내용은 이 항목의 뒷부분에 있는 *assemblyListFile* 내용 예제를 참조하세요.|  
  
|옵션|설명|  
|------------|-----------------|  
|**/cdl**|다운로드 캐시의 내용을 삭제합니다.|  
|**/f**|어셈블리를 강제로 다시 설치하려면 **/i** 또는 **/il** 옵션과 함께 이 옵션을 지정합니다. 동일한 이름의 어셈블리가 전역 어셈블리 캐시에 이미 있으면 해당 어셈블리를 덮어씁니다.|  
|**/h**[**elp**]|이 도구의 명령 구문 및 옵션을 표시합니다.|  
|**/i** *assemblyPath*|전역 어셈블리 캐시에 어셈블리를 설치합니다.|  
|**/if** *assemblyPath*|전역 어셈블리 캐시에 어셈블리를 설치합니다. 동일한 이름의 어셈블리가 전역 어셈블리 캐시에 이미 있으면 해당 어셈블리를 덮어씁니다.<br /><br /> 이 옵션을 지정하는 것은 **/i** 및 **/f** 옵션을 함께 지정하는 것과 같습니다.|  
|**/il** *assemblyListFile*|*assemblyListFile*에 지정된 하나 이상의 어셈블리를 전역 어셈블리 캐시에 설치합니다.|  
|**/ir** *assemblyPath*<br /><br /> *scheme*<br /><br /> *id*<br /><br /> *description*|어셈블리를 전역 어셈블리 캐시에 설치하고 어셈블리 수를 계산하는 참조를 추가합니다. 이 옵션과 함께 *assemblyPath*, *scheme*, *id* 및 *description* 매개 변수를 지정해야 합니다. 이러한 매개 변수에 대해 지정할 수 있는 유효한 값에 대한 설명은 **/r** 옵션을 참조하세요.<br /><br /> 이 옵션을 지정하는 것은 **/i** 및 **/r** 옵션을 함께 지정하는 것과 같습니다.|  
|**/l** [*assemblyName*]|전역 어셈블리 캐시의 내용을 나열합니다. *assemblyName* 매개 변수를 지정하면 이 도구에서는 해당 이름과 일치하는 어셈블리만 나열합니다.|  
|**/ldl**|다운로드된 파일 캐시의 내용을 나열합니다.|  
|**/lr** [*assemblyName*]|모든 어셈블리와 해당 참조 횟수를 나열합니다. *assemblyName* 매개 변수를 지정하면 이 도구에서는 해당 이름 및 해당 참조 횟수와 일치하는 어셈블리만 나열합니다.|  
|**/nologo**|Microsoft 시작 배너를 표시하지 않습니다.|  
|**/r** [*assemblyName &#124; assemblyPath*]<br /><br /> *scheme*<br /><br /> *id*<br /><br /> *description*|설치 또는 제거할 어셈블리에 대해 추적된 참조를 지정합니다. **/i**, **/il**, **/u** 또는 **/ul** 옵션과 함께 이 옵션을 지정합니다.<br /><br /> 어셈블리를 설치하려면 이 옵션과 함께 *assemblyPath*, *scheme*, *id* 및 *description* 매개 변수를 지정합니다. 어셈블리를 제거하려면 *assemblyName*, *scheme*, *id* 및 *description* 매개 변수를 지정합니다.<br /><br /> 어셈블리에 대한 참조를 제거하려면 어셈블리가 설치될 때 **/i** 및 **/r**(또는 **/ir**) 옵션으로 지정된 것과 동일한 *scheme*, *id* 및 *description* 매개 변수를 지정해야 합니다. 어셈블리를 제거할 때 해당 어셈블리가 제거할 마지막 참조이고 Windows Installer에 어셈블리에 대한 미해결 참조가 없으면 이 도구에서는 전역 어셈블리 캐시에서 어셈블리를 제거합니다.<br /><br /> *scheme* 매개 변수는 설치 스키마의 유형을 지정합니다. 다음 값 중 하나를 지정할 수 있습니다.<br /><br /> -   UNINSTALL_KEY: 설치 관리자에서 응용 프로그램을 Microsoft Windows의 [프로그램 추가/제거]에 추가하는 경우 이 값을 지정합니다. 이렇게 하면 HKLM\Software\Microsoft\Windows\CurrentVersion에 레지스트리 키가 추가되고 해당 응용 프로그램이 프로그램 추가/제거 제어판에 추가됩니다.<br />-   FILEPATH: 설치 관리자에서 응용 프로그램을 [프로그램 추가/제거]에 추가하지 않는 경우 이 값을 지정합니다.<br />-   OPAQUE: 설치 시나리오에 레지스트리 키 또는 파일 경로 제공이 적용되지 않는 경우 이 값을 지정합니다. 이 값을 사용하면 *id* 매개 변수에 대해 사용자 지정 정보를 지정할 수 있습니다.<br /><br /> *id* 매개 변수에 대해 지정할 값은 다음과 같이 *scheme* 매개 변수에 지정되는 값에 따라 결정됩니다.<br /><br /> -   *scheme* 매개 변수에 대해 UNINSTALL_KEY를 지정하는 경우 HKLM\Software\Microsoft\Windows\CurrentVersion 레지스트리 키에 설정된 응용 프로그램의 이름을 지정합니다. 예를 들어, 레지스트리 키가 HKLM\Software\Microsoft\Windows\CurrentVersion\MyApp인 경우 *id* 매개 변수에 대해 MyApp을 지정합니다.<br />-   *scheme* 매개 변수에 대해 FILEPATH를 지정하는 경우 어셈블리를 설치하는 실행 파일의 전체 경로를 *id* 매개 변수로 지정합니다.<br />-   *scheme* 매개 변수에 대해 OPAQUE를 지정하는 경우 데이터의 모든 부분을 *id* 매개 변수로 제공할 수 있습니다. 데이터는 큰따옴표("")로 묶어서 지정해야 합니다.<br /><br /> *description* 매개 변수를 사용하면 설치할 응용 프로그램에 대한 설명 텍스트를 지정할 수 있습니다. 이 정보는 참조가 열거될 때 표시됩니다.|  
|**/silent**|모든 출력을 표시하지 않습니다.|  
|**/u** *assemblyName*|전역 어셈블리 캐시에서 어셈블리를 제거합니다.|  
|**/uf** *assemblyName*|어셈블리에 대한 모든 참조를 제거하여 지정된 어셈블리를 강제로 제거합니다.<br /><br /> 이 옵션을 지정하는 것은 **/u** 및 **/f** 옵션을 함께 지정하는 것과 같습니다. **참고:** Microsoft Windows Installer를 사용하여 설치한 어셈블리는 이 옵션으로 제거할 수 없습니다. 이 작업을 시도하면 오류 메시지가 표시됩니다.|  
|**/ul** *assemblyListFile*|전역 어셈블리 캐시에서 *assemblyListFile*에 지정된 하나 이상의 어셈블리를 제거합니다.|  
|**/u**[**ngen**] *assemblyName*|전역 어셈블리 캐시에서 지정된 어셈블리의 설치를 제거합니다. 지정된 어셈블리가 기존의 참조 횟수를 갖는 경우 이 도구에서는 해당 참조 횟수를 표시하고 전역 어셈블리 캐시에서 해당 어셈블리를 제거하지 않습니다. **참고:** .NET Framework 버전 2.0에서 `/ungen`은 지원되지 않습니다. 대신에 [Ngen.exe(네이티브 이미지 생성기)](../../../docs/framework/tools/ngen-exe-native-image-generator.md)의 `uninstall` 명령을 사용합니다. <br /><br /> .NET Framework 버전 1.0 및 1.1에서 **/ungen**을 지정하면 Gacutil.exe가 네이티브 이미지 캐시에서 어셈블리를 제거합니다. 이 캐시는 [Ngen.exe(네이티브 이미지 생성기)](../../../docs/framework/tools/ngen-exe-native-image-generator.md)를 사용하여 만들어진 어셈블리의 네이티브 이미지를 저장합니다.|  
|**/ur** *assemblyName*<br /><br /> *scheme*<br /><br /> *id*<br /><br /> *description*|전역 어셈블리 캐시에서 지정된 어셈블리의 참조를 제거합니다. 어셈블리에 대한 참조를 제거하려면 어셈블리가 설치될 때 **/i** 및 **/r**(또는 **/ir)** 옵션으로 지정된 것과 동일한 *scheme*, *id* 및 *description* 매개 변수를 지정해야 합니다. 이러한 매개 변수에 대해 지정할 수 있는 유효한 값에 대한 설명은 **/r** 옵션을 참조하세요.<br /><br /> 이 옵션을 지정하는 것은 **/u** 및 **/r** 옵션을 함께 지정하는 것과 같습니다.|  
|**/?**|이 도구의 명령 구문 및 옵션을 표시합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  Gacutil.exe를 사용하려면 관리자 권한이 있어야 합니다.  
  
 특히, Gacutil.exe를 사용하면 캐시에 어셈블리를 설치하거나, 캐시에서 어셈블리를 제거하거나, 캐시의 내용을 나열할 수 있습니다.  
  
 Gacutil.exe는 Windows Installer에서 지원하는 참조 횟수 계산 스키마와 비슷한 참조 횟수 계산 기능을 지원하는 옵션을 제공합니다. Gacutil.exe를 사용하여 동일한 어셈블리를 설치하는 두 개의 응용 프로그램을 설치할 수 있습니다. 이 도구는 어셈블리에 대한 참조의 개수를 추적합니다. 따라서 어셈블리는 두 응용 프로그램이 모두 제거될 때까지 컴퓨터에 남아 있습니다. 실제 제품 설치를 위해 Gacutil.exe를 사용하는 경우 참조 횟수 계산을 지원하는 옵션을 사용합니다. 어셈블리를 설치하고 개수를 계산하는 참조를 추가하려면 **/i** 및 **/r** 옵션을 함께 사용합니다. 어셈블리에 대한 참조 횟수를 제거하려면 **/u** 및 **/r** 옵션을 함께 사용합니다. **/i** 및 **/u** 옵션을 단독으로 사용하면 참조 횟수 계산이 지원되지 않습니다. 이러한 옵션은 제품 개발 중에 사용하는 것이 적절하며 실제 제품을 설치할 때는 사용하지 않는 것이 좋습니다.  
  
 ANSI 텍스트 파일에 저장된 어셈블리 목록을 설치 또는 제거하려면 **/il** 또는 **/ul** 옵션을 사용합니다. 텍스트 파일의 내용은 올바른 서식으로 지정되어 있어야 합니다. 텍스트 파일을 사용하여 어셈블리를 설치하려면 각 어셈블리 경로를 해당 파일에서 별도의 줄에 지정하십시오. 다음 예제에서는 설치할 어셈블리를 포함하는 파일의 내용을 보여 줍니다.  
  
```  
myAssembly1.dll  
myAssembly2.dll  
myAssembly3.dll  
```  
  
 텍스트 파일을 사용하여 어셈블리를 제거하려면 각 어셈블리의 정규화된 어셈블리 이름을 해당 파일에서 별도의 줄에 지정하십시오. 다음 예제에서는 제거할 어셈블리를 포함하는 파일의 내용을 보여 줍니다.  
  
```  
myAssembly1,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab  
myAssembly2,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab  
myAssembly3,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab  
```  
  
## <a name="examples"></a>예제  
 다음 명령은 전역 어셈블리 캐시에 `mydll.dll` 어셈블리를 설치합니다.  
  
```  
gacutil /i mydll.dll  
```  
  
 다음 명령은 해당 어셈블리에 대한 참조 횟수가 없는 경우 전역 어셈블리 캐시에서 어셈블리 `hello`를 제거합니다.  
  
```  
gacutil /u hello  
```  
  
 앞의 명령을 사용하면 어셈블리 이름이 전부 지정되지 않기 때문에 어셈블리 캐시에서 둘 이상의 어셈블리를 제거할 수도 있습니다. 예를 들어, 캐시에 `hello`의 1.0.0.0 버전 및 3.2.2.1 버전이 모두 설치된 경우 `gacutil /u hello` 명령을 사용하면 두 어셈블리가 모두 제거됩니다.  
  
 둘 이상의 어셈블리가 제거되지 않도록 하려면 다음 예제를 사용합니다. 이 명령을 사용하면 완전히 지정된 버전 번호, culture 및 공개 키와 일치하는 `hello` 어셈블리만 제거됩니다.  
  
```  
gacutil /u hello, Version=1.0.0.1, Culture="de",PublicKeyToken=45e343aae32233ca  
```  
  
 다음 명령은 파일 `assemblyList.txt`에 지정된 어셈블리를 전역 어셈블리 캐시에 설치합니다.  
  
 `gacutil /il assemblyList.txt`  
  
 다음 명령은 전역 어셈블리 캐시에서 파일 `assemblyList.txt`에 지정된 어셈블리를 제거합니다.  
  
 `gacutil /ul assemblyList.txt`  
  
 다음 명령은 전역 어셈블리 캐시에 `myDll.dll`을 설치하고 해당 어셈블리 개수를 계산하는 참조를 추가합니다. 어셈블리 `myDll.dll`은 응용 프로그램 `MyApp`에 의해 사용됩니다. `UNINSTALL_KEY MyApp` 매개 변수는 Windows의 프로그램 추가/제거에 `MyApp`을 추가하는 레지스트리 키를 지정합니다. description 매개 변수는 `My Application Description`으로 지정됩니다.  
  
```  
gacutil /i /r myDll.dll UNINSTALL_KEY MyApp "My Application Description"  
```  
  
 다음 명령은 전역 어셈블리 캐시에 `myDll.dll`을 설치하고 해당 어셈블리 개수를 계산하는 참조를 추가합니다. scheme 매개 변수 `FILEPATH`와 id 매개 변수 `c:\applications\myApp\myApp.exe`는 `myDll.dll.`을 설치 중인 응용 프로그램 경로를 지정합니다. description 매개 변수는 `MyApp`으로 지정됩니다.  
  
 `gacutil /i /r myDll.dll FILEPATH c:\applications\myApp\myApp.exe MyApp`  
  
 다음 명령은 전역 어셈블리 캐시에 `myDll.dll`을 설치하고 해당 어셈블리 개수를 계산하는 참조를 추가합니다. scheme 매개 변수 `OPAQUE`를 사용하면 id 및 description 매개 변수를 사용자 지정할 수 있습니다.  
  
```  
gacutil /i /r mydll.dll OPAQUE "Insert custom application details here" "Insert Custom description information here"  
```  
  
 다음 명령은 응용 프로그램 `myDll.dll`에 의한 `myApp`에 대한 참조를 제거합니다. 이 참조가 어셈블리에 대한 마지막 참조인 경우 전역 어셈블리 캐시에서 해당 어셈블리도 제거됩니다.  
  
 `gacutil /u /r myDll.dll FILEPATH c:\applications\myApp\myApp.exe MyApp`  
  
 다음 명령은 전역 어셈블리 캐시의 내용을 나열합니다.  
  
```  
gacutil /l  
```  
  
## <a name="see-also"></a>참고 항목  
 [도구](../../../docs/framework/tools/index.md)   
 [전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md)   
 [Regasm.exe(어셈블리 등록 도구)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)   
 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

