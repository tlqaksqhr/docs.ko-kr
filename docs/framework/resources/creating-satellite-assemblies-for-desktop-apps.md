---
title: "데스크톱 응용 프로그램용 위성 어셈블리 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "응용 프로그램 배포[.NET Framework], 리소스"
  - "리소스 파일, 배포"
  - "허브 및 스포크 리소스 배포 모델"
  - "리소스 파일, 패키징"
  - "응용 프로그램 리소스, 패키징"
  - "공용 키, 가져오기"
  - "위성 어셈블리"
  - "어셈블리[.NET Framework], 서명"
  - "응용 프로그램 리소스, 배포"
  - "Al.exe"
  - "GAC(전역 어셈블리 캐시), 위성 어셈블리"
  - "어셈블리 링커"
  - "위성 어셈블리의 디렉터리 위치"
  - "전역 어셈블리 캐시, 위성 어셈블리"
  - "응용 프로그램 리소스 패키징"
  - "위성 어셈블리 컴파일"
  - "어셈블리 다시 서명"
ms.assetid: 8d5c6044-2919-41d2-8321-274706b295ac
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 데스크톱 응용 프로그램용 위성 어셈블리 만들기
리소스 파일은 지역화 된 응용 프로그램에서 중심 역할을 합니다.  응용 프로그램에서 사용자의 언어와 문화, 문자열, 이미지 및 기타 데이터를 표시 하고 사용자의 언어 또는 문화권에 대한 리소스를 사용할 수 없는 경우 대체 데이터를 제공 하기 위해 사용 합니다.  .NET Framework에서는 허브와 스포크 모델을 사용하여 리소스를 위치시키고 검색 합니다.  허브는 지역화할 수 없는 실행 코드와 중립 또는 기본 문화권이라고 하는 단일 문화권의 리소스를 포함하는 주 어셈블리입니다.  기본 문화권은 지역화 된 리소스가 없는 경우에 응용 프로그램에 대한 대체 문화권으로 사용 됩니다.  응용 프로그램의 기본 culture의 culture를 지정 하기 위해 <xref:System.Resources.NeutralResourcesLanguageAttribute> 특성을 사용합니다.  각 스포크는 단일 지역 문화권의 리소스를 포함하지만 코드는 포함하지 않는 위성 어셈블리에 연결됩니다.  위성 어셈블리는 주 어셈블리의 일부가 아니므로 응용 프로그램의 주 어셈블리를 바꾸지 않고도 특정 문화권에 해당하는 리소스를 손쉽게 바꾸거나 업데이트할 수 있습니다.  
  
> [!NOTE]
>  응용 프로그램의 기본 문화권의 리소스를 위성 어셈블리에 저장할 수도 있습니다.  이것을 하기 위해, <xref:System.Resources.NeutralResourcesLanguageAttribute> 특성을 <xref:System.Resources.UltimateResourceFallbackLocation?displayProperty=fullName> 값으로 배정 합니다.  
  
## 위성 어셈블리의 이름 및 위치  
 허브와 스포크 모델을 사용하려면 리소스를 쉽게 찾아서 사용할 수 있도록 특정 위치에 두어야 합니다.  리소스 컴파일과 이름 지정을 제대로 하지 않거나 리소스를 정확한 위치에 두지 않으면 공용 언어 런타임에서는 이 리소스를 찾을 수 없으며 대신 기본 문화 리소스를 사용 합니다.  .NET Framework 리소스 관리자는  <xref:System.Resources.ResourceManager> 개체로 나타내어 지는데, 자동으로 지역화 된 리소스에 액세스 하는 데 사용 됩니다.  리소스 관리자는 다음 사항이 필요 합니다:  
  
-   단일 위성 어셈블리는 특정 문화권에 대한 모든 리소스를 포함 해야 합니다.  즉, 단일 이진 .resources 파일로 여러 .resx 또는 .txt 파일로 컴파일해야 합니다.  
  
-   해당 문화권의 리소스를 저장 하는 각 지역화 된 문화권에 대한 응용 프로그램 디렉터리에 있는 별도 하위 디렉터리 이어야 합니다.  하위 디렉터리 이름은 문화권 이름과 동일 해야 합니다.  또는 전역 어셈블리 캐시에 위성 어셈블리를 저장할 수 있습니다.  이 경우 문화권 정보 구성 요소 어셈블리의 강력한 이름을 culture를 지정 해야 합니다. \(이 항목의 뒷부분에 있는 [위성 어셈블리를 전역 어셈블리 캐시에 설치](#SN) 를 참고하십시오.\)  
  
    > [!NOTE]
    >  하위 culture의 리소스 응용 프로그램의 경우, 각 하위 culture를 별도 응용 프로그램 디렉터리의 하위 디렉터리에 배치 합니다.  주 culture 디렉터리의 아래 하위 디렉터리에 하위 culture를 두면 안 됩니다.  
  
-   위성 어셈블리는 응용 프로그램과 동일한 이름을 가져야 하고 ". resources.dll"을 파일 이름 확장명으로 사용 해야 합니다.  예를 들어, Example.exe 응용 프로그램 이름이 인 경우, 각 위성 어셈블리의 이름은 Example.resources.dll 이어야 합니다.  위성 어셈블리 이름이 해당 리소스 파일의 문화권을 나타내지 않는다는 것에 주의합니다.  그러나, 위성 어셈블리의 culture가 지정된 디렉터리에 나타납니다.  
  
-   위성 어셈블리의 culture에 대한 정보는 어셈블리의 메타 데이터에 포함 되어야 합니다.  위성 어셈블리의 메타 데이터에서 문화권 이름을 저장하기 위해, `/culture` 옵션을 [어셈블리 링커](../../../docs/framework/tools/al-exe-assembly-linker.md) 를 위성 어셈블리에 리소스를 포함할 때 지정해야 합니다.  
  
 다음 그림에서는 [전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md)에 설치하지 않는 응용 프로그램에 대한 위치 요구 사항 및 샘플 디렉터리 구조를 보여 줍니다.  .txt 및 .resources 파일 확장명을 가진 항목은 최종 응용 프로그램과 함께 제공되지 않습니다.  이러한 항목은 최종 위성 리소스 어셈블리를 만드는 데 사용되는 중간 리소스 파일입니다.  이 예제에서는 .resx 파일로 .txt 파일을 대체할 수 있습니다.  자세한 내용은 [리소스 패키징 및 배포](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)를 참조하십시오.  
  
 ![위성 어셈블리](../../../docs/framework/resources/media/satelliteassemblydir.gif "satelliteassemblydir")  
위성 어셈블리 디렉터리  
  
## 위성 어셈블리 컴파일  
 텍스트 파일이나 이진 .resources 파일에 리소스를 포함 하는 XML \(.resx\) 파일을 컴파일 하기 위해 [리소스 파일 생성기 \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 를 사용합니다.  [어셈블리 링커\(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 .resources 파일을 위성 어셈블리로 컴파일할 수 있습니다.  Al.exe는 사용자가 지정한 .resources 파일로부터 어셈블리를 만듭니다.  위성 어셈블리는 리소스만 포함 할 수 있습니다. 어떠한 실행 코드도 포함할 수 없습니다.  
  
 다음 Al.exe 명령은 독일 리소스 파일 strings.de.resources에서 `Example` 응용 프로그램에 대한 위성 어셈블리를 만듭니다.  
  
```  
al /target:lib /embed:strings.de.resources /culture:de /out:Example.resources.dll  
```  
  
 다음 Al.exe 명령은 파일 strings.de.resources에서 `Example` 응용 프로그램에 대한 위성 어셈블리도 만듭니다.  **\/template** 옵션을 사용 하면 위성 어셈블리가 부모 어셈블리\(Example.dll\) 로부터 culture 관련 정보를 제외한 모든 어셈블리 메타 데이터를 상속 합니다.  
  
```  
al /target:lib /embed:strings.de.resources /culture:de /out:Example.resources.dll /template:Example.dll  
```  
  
 다음 표에서는 이러한 명령에 사용된 Al.exe 옵션을 더 자세히 설명합니다.  
  
|옵션|설명|  
|--------|--------|  
|**\/target:**lib|위성 어셈블리가 라이브러리 파일\(.dll\)로 컴파일되도록 지정합니다.  위성 어셈블리 코드가 실행 가능한 응용 프로그램을 포함하고 주 어셈블리가 아니기 때문에, 위성 어셈블리를 Dll로 저장 해야 합니다.|  
|**\/embed:**strings.de.resources|Al.exe로 어셈블리를 컴파일하는 경우 리소스 파일의 이름을 지정합니다.  위성 어셈블리에 여러 개의 .resources 파일을 포함할 수 있지만, 허브 및 스포크 모델을 따르는 경우, 각 culture에 대해 하나의 위성 어셈블리를 컴파일해야 합니다.  그러나, 문자열 및 개체에 대해 별도의 .resources 파일을 만들 수 있습니다.|  
|**\/culture:**de|컴파일한 리소스의 culture를 지정 합니다.  공용 언어 런타임은 지정된 culture의 리소스를 검색하는 경우 이 정보를 사용합니다.  이 옵션을 생략한 경우, Al.exe는 리소스를 컴파일하지만 런타임에서는 사용자가 리소스를 요청할 때 해당 리소스를 찾을 수 없습니다.|  
|**\/out:**Example.resources.dll|출력 파일의 이름을 지정합니다.  이 이름은 명명 표준 *baseName*.resources.*extension*을 따라야 합니다. 여기서 *baseName* 은 주 에셈블리의 이름이고 *extension* 은 \(.dll\)와 같은 유효한 파일 이름 확장명입니다.  런타임이 출력 파일 이름을 기반으로 위성 어셈블리의 culture를 결정할 수 없는 경우 지정하기 위해 **\/culture** 옵션을 사용 합니다.|  
|**\/template:**Example.dll|위성 어셈블리가 culture 필드를 제외하고 모든 어셈블리 메타데이터를 상속할 어셈블리를 지정합니다.  이 옵션은 [강력한 이름](../../../docs/framework/app-domains/strong-named-assemblies.md)을 가진 어셈블리를 지정할 때에만 위성 어셈블리에 영향을 미칩니다.|  
  
 Al.exe에서 사용할 수 있는 전체 옵션 목록을 보려면 [어셈블리 링커\(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 참조하십시오.  
  
## 위성 어셈블리: 예  
 다음은 지역화 된 인사말이 들어 있는 메시지 상자를 표시 하는 간단한 "Hello world" 예제입니다.  이 예제에서는 영어 \(미국\), 프랑스어 \(프랑스\) 및 러시아어 \(러시아\) 문화권에 대한 리소스가 포함되고 대체 \(fallback\) culture는 영어 입니다.  이 예제를 만들기 위해, 다음을 수행합니다.  
  
1.  기본 문화권의 리소스를 포함하는 Greeting.resx 또는 Greeting.txt 라는 리소스 파일을 만듭니다.  이 파일에 있는 "Hello world\!"이 값인 `HelloString` 단일 문자열을 저장 합니다.  
  
2.  영어\(en\)이 응용 프로그램의 기본 문화임을 나타내기 위해, 다음 <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> 특성을 응용 프로그램의 AssemblyInfo 파일 또는 응용 프로그램의 주 어셈블리로 컴파일 될 주 소스 파일에 추가합니다.  
  
     [!code-csharp[Conceptual.Resources.Locating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.locating/cs/assemblyinfo.cs#2)]
     [!code-vb[Conceptual.Resources.Locating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.locating/vb/assemblyinfo.vb#2)]  
  
3.  예를 들어 "en\-US", "fr\-FR" 및 "ru\-RU" 문화권을 응용 프로그램에 다음과 같이 추가할 수 있습니다.  
  
    -   "en\-US" 또는 영어\(미국\) 문화권을 지원하려면 Greeting.en\-US.resx 또는 Greeting.en\-US.txt 라는 리소스 파일을 만들어 값이 "Hi world\!"인 `HelloString` 이라는 단일 문자열에 저장합니다.  
  
    -   "fr\-FR" 또는 프랑스어\(프랑스\) 문화권을 지원하려면 Greeting.fr\-FR.resx 또는 Greeting.fr\-FR.txt 라는 리소스 파일을 만들어 값이 "Salut tout le monde\!"인 `HelloString`이라는 단일 문자열에 저장합니다.  
  
    -   "ru\-RU" 또는 러시아어\(러시아\) 문화권을 지원하려면 Greeting.ru\-RU.resx 또는 Greeting.ru\-RU.txt 라는 리소스 파일을 만들어 값이 "Всем привет\!"인 `HelloString`이라는 단일 문자열에 저장합니다.  
  
4.  [Resgen.exe](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 을 사용하여 각 텍스트 또는 XML 리소스 파일을 이진 .resources 파일로 컴파일할 수 있습니다.  출력은 .resx 또는.txt 파일과 동일한 루트 파일 이름을 가지고 있지만 .resources 확장명과는 다른 파일의 집합입니다.  Visual Studio을 사용하여 예제를 만들면 컴파일 프로세스는 자동으로 처리 됩니다.  Visual Studio을 사용 하지 않는 경우, .resources 파일을 .resx 파일을 컴파일하는 데 다음 명령을 실행 합니다.  
  
    ```  
  
    resgen Greeting.resx  
    resgen Greeting.en-us.resx  
    resgen Greeting.fr-FR.resx  
    resgen Greeting.ru-RU.resx  
  
    ```  
  
     리소스가 XML 파일 대신 텍스트 파일인 경우 .resx 확장명이 .txt로 바꿉니다.  
  
5.  다음 소스 코드를 기본 문화권의 리소스를 응용 프로그램의 주 어셈블리로 컴파일하십시오.  
  
    > [!IMPORTANT]
    >  예제를 만들기 위해 Visual Studio 대신 명령 줄을 사용한다면, <xref:System.Resources.ResourceManager> 클래스 생성자를 `ResourceManager rm = new ResourceManager("Greetings",``typeof(Example).Assembly);` 과 같이 호출을 수정해야 합니다.  
  
     [!code-csharp[Conceptual.Resources.Locating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.locating/cs/program.cs#1)]
     [!code-vb[Conceptual.Resources.Locating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.locating/vb/module1.vb#1)]  
  
     응용 프로그램 이름이 Example이고 명령줄에서 컴파일하는 경우 C\# 컴파일러에 대한 명령은 다음과 같습니다.  
  
    ```  
    csc Example.cs /res:Greeting.resources  
    ```  
  
     해당 Visual Basic 컴파일러 명령:  
  
    ```  
    vbc Example.vb /res:Greeting.resources  
    ```  
  
6.  응용 프로그램에 의해 지원되는 각 지역화 된 문화권에 대한 주 응용 프로그램 디렉토리에서 하위 디렉터리를 만듭니다.  EN\-US, FR\-FR, RU\-RU 하위 디렉터리를 만들어야 합니다.  Visual Studio은 컴파일 프로세스의 일부로 이러한 하위 디렉터리를 자동으로 만듭니다.  
  
7.  각 문화권별 .resources 파일을 위성 어셈블리로 포함 하고 해당 디렉터리에 저장 합니다.  .Resources 파일 각각에 대해 이 작업을 수행 하는 명령은 다음과 같습니다.  
  
    ```  
    al /target:lib /embed:Greeting.culture.resources /culture:culture /out:culture\Example.resources.dll  
    ```  
  
     여기서 *culture*은 리소스가 위성 어셈블리에 포함 된 문화권 이름입니다.  Visual Studio은 자동으로 이 프로세스를 처리 합니다.  
  
 예제를 실행할 수 있습니다.  지원되는 문화권 중 하나를 현재 문화권으로 임의로 만들고 지역화 된 인사말을 표시 합니다.  
  
<a name="SN"></a>   
## 전역 어셈블리 캐시에 위성 어셈블리 설치  
 로컬 응용 프로그램 하위 디렉터리에 어셈블리를 설치 하는 대신, 전역 어셈블리 캐시에 설치할 수 있습니다.  클래스 라이브러리 및 클래스 라이브러리 리소스 어셈블리가 여러 응용 프로그램에서 사용되는 경우 이것은 특히 유용 합니다.  
  
 강력한 이름이 필요한 전역 어셈블리 캐시에 어셈블리를 설치 합니다.  강력한 이름의 어셈블리는 올바른 공개\/개인 키 쌍으로 서명됩니다.  바인딩 요청을 만족시키는 데 사용할 어셈블리를 결정하기 위해 런타임에서 사용하는 버전 정보가 포함됩니다.  강력한 이름과 버전 관리에 대한 자세한 내용은 [어셈블리 버전 관리](../../../docs/framework/app-domains/assembly-versioning.md)를 참조 하십시오.  강력한 이름에 대한 자세한 내용은 [강력한 이름의 어셈블리](../../../docs/framework/app-domains/strong-named-assemblies.md)를 참조하십시오.  
  
 응용 프로그램을 개발하는 경우 최종 공개\/개인 키 쌍에 대한 액세스 권한을 갖게 되지는 않습니다.  위성 어셈블리를 전역 어셈블리 캐시에 설치하고 제대로 동작하게 하려면 서명 연기라는 기법을 사용하면 됩니다.  어셈블리 서명을 연기하면 빌드할 때 강력한 이름 시그니처에 사용할 파일 공간이 예약됩니다.  나중에 최종 공개\/개인 키 쌍을 사용할 수 있을 때까지 실제 서명이 연기됩니다.  서명 연기에 대한 자세한 내용은 [어셈블리 서명 연기](../../../docs/framework/app-domains/delay-sign-assembly.md)를 참조하십시오.  
  
### 공개 키 얻기  
 어셈블리 서명을 연기하려면 공개 키에 액세스할 수 있어야 합니다.  최종 서명을 수행하는 회사 내 조직으로부터 실제 공개 키를 얻거나 [강력한 이름 도구\(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)를 사용하여 공개 키를 만들 수 있습니다.  
  
 다음 Sn.exe 명령은 테스트 공개\/개인 키 쌍을 만듭니다.  **– k** 옵션은 Sn.exe가 새 키 쌍을 작성하고 TestKeyPair.snk 라는 파일에 저장 해야 하는 것을 지정 합니다.  
  
```  
sn –k TestKeyPair.snk   
```  
  
 테스트 키 쌍을 포함하는 파일에서 공개 키를 추출할 수 있습니다.  다음 명령은 TestKeyPair.snk에서 공개 키를 추출 하고 PublicKey.snk에 저장합니다:  
  
```  
sn –p TestKeyPair.snk PublicKey.snk  
```  
  
### 어셈블리 서명 연기  
 공개 키를 얻었거나 만든 후에는, [어셈블리 링커\(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 어셈블리를 컴파일하고 서명 연기를 지정할 수 있습니다.  
  
 다음 Al.exe 명령은 strings.ja.resources 파일로부터 StringLibrary 응용 프로그램에 대한 강력한 이름의 위성 어셈블리를 만듭니다.  
  
```  
al /target:lib /embed:strings.ja.resources /culture:ja /out:StringLibrary.resources.dll /delay+ /keyfile:PublicKey.snk  
```  
  
 **\/delay\+** 옵션은 어셈블리 링커가 어셈블리 서명을 연기해야 하는 것을 지정합니다.  **\/keyfile:** 옵션은 어셈블리 서명을 연기하기 위해 사용할 공개 키를 포함하는 키 파일의 이름을 지정합니다.  
  
### 어셈블리 다시 서명  
 응용 프로그램을 배포 하기 전에, 실제 키 쌍으로 지연 서명된 위성 어셈블리를 다시 서명 해야 합니다.  Sn.exe를 사용하여 이를 수행할 수 있습니다.  
  
 다음 Sn.exe 명령은 RealKeyPair.snk 파일에 저장된 실제 키 쌍으로 StringLibrary.resources.dll에 서명합니다.  **–R** 옵션은 이전에 서명했거나 서명이 연기된 어셈블리에 다시 서명하도록 지정합니다.  
  
```  
sn –R StringLibrary.resources.dll RealKeyPair.snk   
```  
  
### 전역 어셈블리 캐시에 위성 어셈블리 설치  
 런타임이 리소스 대체\(fallback\) 프로세스에서 검색할 때, 가장 먼저 [전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md)에서 찾습니다. 자세한 내용은 [리소스 패키징 및 배포](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)의 "리소스 대체 프로세스" 단원을 참조하십시오. 위성 어셈블리를 강력한 이름으로 서명 되는 즉시 설치할 수 있습니다. [전역 어셈블리 캐시 도구 \(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 이용하여 전역 어셈블리 캐시에서 설치될 수 있습니다.  
  
 다음 Gacutil.exe 명령은 StringLibrary.resources.dll를 전역 어셈블리 캐시에 설치합니다.  
  
```  
gacutil /i:StringLibrary.resources.dll  
```  
  
 **\/i** 옵션은 Gacutil.exe가 지정된 어셈블리를 전역 어셈블리 캐시에 설치하도록 지정합니다.  위성 어셈블리가 캐시에 설치된 후, 리소스는 위성 어셈블리를 사용 하도록 설계 된 모든 응용 프로그램에 사용할 수 있도록 포함합니다.  
  
### 전역 어셈블리 캐시에 리소스: 예  
 다음 예제에서는 .NET Framework 클래스 라이브러리에서 메서드를 사용 하여 리소스 파일에서 추출하고 지역화 된 인사를 반환 합니다.  라이브러리 및 리소스를 전역 어셈블리 캐시에 등록 됩니다.  예제는 프랑스어\(프랑스\) 및 영어\(미국\), 러시아어\(러시아\), 영미 문화권에 대한 리소스가 포함됩니다.  영어는 기본 culture입니다. 리소스는 주 어셈블리에 저장 됩니다.  처음 예제는 라이브러리 및 공개 키를 가진 위성 어셈블리를 서명한 다음 공개\/개인 키 쌍을 사용 하여 다시 서명 합니다.  이 예제를 만들기 위해, 다음을 수행합니다.  
  
1.  Visual Studio를 사용 하지 않는 경우, 다음 [강력한 이름 도구 \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 명령을 ResKey.snk 라는 공개\/개인 키 쌍을 만들기 위해 사용합니다.  
  
    ```  
    sn –k ResKey.snk  
    ```  
  
     Visual Studio를 사용 하는 경우, 키 파일을 생성하기 위해 프로젝트의 **서명** 탭 **속성** 대화 상자를 사용합니다.  
  
2.  다음 [강력한 이름 도구 \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 명령을 사용하여 PublicKey.snk 공개 키 파일을 만듭니다.  
  
    ```  
    sn –p ResKey.snk PublicKey.snk  
    ```  
  
3.  기본 문화권의 리소스를 포함할 Strings.resx 리소스 파일을 만듭니다.  파일에 "How do you do?" 의 값을 가진 `Greeting` 이름의 단일 문자열을 저장합니다.  
  
4.  "en"이 응용 프로그램의 기본 문화권임을 나타내려면, 다음 <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> 특성을 응용 프로그램의 AssemblyInfo 파일이나 응용 프로그램의 주 어셈블리로 컴파일될 소스 코드 파일 중 하나에도 추가해야 합니다.  
  
     [!code-csharp[Conceptual.Resources.Satellites#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/stringlibrary.cs#2)]
     [!code-vb[Conceptual.Resources.Satellites#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/stringlibrary.vb#2)]  
  
5.  예를 들어 "en\-US", "fr\-FR" 및 "ru\-RU" 문화권을 응용 프로그램에 다음과 같이 추가합니다.  
  
    -   "en\-US" 또는 영어\(미국\) 문화권을 지원하려면, Strings.en\-US.resx 또는 Strings.en\-US.txt 라는 리소스 파일을 만들어 값이 "Hi world\!"인 `Greeting`이라는 단일 문자열에 저장합니다.  
  
    -   "fr\-FR" 또는 프랑스어\(프랑스\) 문화권을 지원하려면 Strings.fr\-FR.resx 또는 Strings.fr\-FR.txt 라는 리소스 파일을 만들어 값이 ""Bon jour\!" 인 `Greeting`이라는 단일 문자열에 저장합니다.  
  
    -   "ru\-RU" 또는 러시아어\(러시아\) 문화권을 지원하려면 Strings.ru\-RU.resx 또는 Strings.ru\-RU.txt라는 리소스 파일을 만들어 값이 "Привет\!"인 `Greeting`이라는 단일 문자열에 저장합니다.  
  
6.  [Resgen.exe](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 을 사용하여 각 텍스트 또는 XML 리소스 파일을 이진 .resources 파일로 컴파일할 수 있습니다.  출력은 .resx 또는 .txt 파일과 동일한 루트 파일 이름을 가지고 있지만 .resources 확장명과는 다른 파일의 집합입니다.  Visual Studio을 사용하여 예제를 만들면 컴파일 프로세스는 자동으로 처리 됩니다.  Visual Studio을 사용 하지 않는 경우, .resources 파일을 .resx 파일을 컴파일하는 데 다음 명령을 실행 합니다.  
  
    ```  
    resgen filename  
    ```  
  
     여기서 *filename* 은 옵션 경로, 파일 이름 및.resx 또는 텍스트 파일의 확장명 입니다.  
  
7.  StringLibrary.vb 또는 StringLibrary.cs에 대한 다음 소스 코드를 지연 서명된 StringLibrary.dll 라는 라이브러리 어셈블리를 컴파일 합니다.  
  
    > [!IMPORTANT]
    >  예제를 만들기 위해 Visual Studio 대신 명령 줄을 사용한다면,  <xref:System.Resources.ResourceManager> 클래스 생성자를        `ResourceManager rm = new ResourceManager("Strings",` `typeof(Example).Assembly);`로 호출을 수정해야 합니다.  
  
     [!code-csharp[Conceptual.Resources.Satellites#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/stringlibrary.cs#1)]
     [!code-vb[Conceptual.Resources.Satellites#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/stringlibrary.vb#1)]  
  
     C\# 컴파일러 명령:  
  
    ```  
    csc /t:library /resource:Strings.resources /delaysign+ /keyfile:publickey.snk StringLibrary.cs  
    ```  
  
     해당 Visual Basic 컴파일러 명령:  
  
    ```  
    vbc /t:library /resource:Strings.resources /delaysign+ /keyfile:publickey.snk StringLibrary.vb  
    ```  
  
8.  응용 프로그램에 의해 지원되는 각 지역화 된 문화권에 대한 주 응용 프로그램 디렉토리에서 하위 디렉터리를 만듭니다.  EN\-US, FR\-FR, RU\-RU 하위 디렉터리를 만들어야 합니다.  Visual Studio은 컴파일 프로세스의 일부로 이러한 하위 디렉터리를 자동으로 만듭니다.  위성 어셈블리가 모두 같은 파일 이름을 갖기 때문에, 공개\/개인 키 쌍으로 서명 되있을 때까지 각 문화권별 위성 어셈블리를 저장 하는 데 하위 디렉토리가 사용 됩니다.  
  
9. 각 문화권별 .resources 파일을 지연 서명된 위성 어셈블리로 포함 하고 해당 디렉터리에 저장 합니다.  .Resources 파일 각각에 대해 이 작업을 수행 하는 명령은 다음과 같습니다.  
  
    ```  
    al /target:lib /embed:Strings.culture.resources /culture:culture /out:culture\StringLibrary.resources.dll /delay+ /keyfile:publickey.snk  
    ```  
  
     여기서 *culture*은 문화권의 이름입니다.  이 예제에서, 문화권 이름은 EN\-US, FR\-FR, RU\-RU 입니다.  
  
10. [강력한 이름 도구 \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)을 다음과 같이 사용하여 StringLibrary.dll를 다시 서명합니다.  
  
    ```  
    sn –R StringLibrary.dll RealKeyPair.snk  
    ```  
  
11. 개별 위성 어셈블리에 다시 서명 합니다.  이것을 하기 위해, 각 위성 어셈블리에 대해 [강력한 이름 도구 \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 를 다음과 같이 사용합니다.  
  
    ```  
    sn –R StringLibrary.resources.dll RealKeyPair.snk  
    ```  
  
12. 다음 명령을 사용하여 StringLibrary.dll 및 전역 어셈블리 캐시에 있는 각 위성 어셈블리를 등록합니다.  
  
    ```  
    gacutil /i filename  
    ```  
  
     여기서 *filename*은 등록할 실행 파일의 이름입니다.  
  
13. Visual Studio 사용 하는 경우, 새 **콘솔 응용 프로그램** 프로젝트를 `Example` 이름으로 만들고, StringLibrary.dll에 참조와 다음 소스 코드를 추가 하고 컴파일합니다.  
  
     [!code-csharp[Conceptual.Resources.Satellites#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/example.cs#3)]
     [!code-vb[Conceptual.Resources.Satellites#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/example.vb#3)]  
  
     명령 줄에서 컴파일하려면 C\# 컴파일러에서 다음 명령을 사용합니다:  
  
    ```  
    csc Example.cs /r:StringLibrary.dll   
    ```  
  
     Visual Basic의 컴파일러 명령 줄:  
  
    ```  
    vbc Example.vb /r:StringLibrary.dll   
    ```  
  
14. Example.exe를 실행합니다.  
  
## 참고 항목  
 [리소스 패키징 및 배포](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)   
 [어셈블리 서명 연기](../../../docs/framework/app-domains/delay-sign-assembly.md)   
 [Al.exe\(어셈블리 링커\)](../../../docs/framework/tools/al-exe-assembly-linker.md)   
 [Sn.exe\(강력한 이름 도구\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [Gacutil.exe\(전역 어셈블리 캐시 도구\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)   
 [데스크톱 응용 프로그램의 리소스](../../../docs/framework/resources/index.md)