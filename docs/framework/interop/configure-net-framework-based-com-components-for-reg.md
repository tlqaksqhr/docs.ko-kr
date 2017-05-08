---
title: "방법: 등록이 필요 없는 활성화를 위한 .NET Framework 기반 COM 구성 요소 구성 | Microsoft Docs"
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
  - "활성화, 등록 필요 없음"
  - "응용 프로그램 매니페스트[.NET Framework]"
  - "구성 요소[.NET Framework], 매니페스트"
  - "매니페스트[.NET Framework]"
  - "등록이 필요 없는 COM interop, .NET 기반 구성 요소 구성"
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 등록이 필요 없는 활성화를 위한 .NET Framework 기반 COM 구성 요소 구성
.NET Framework 기반 구성 요소에 대한 등록이 필요 없는 활성화 과정은 COM 구성 요소의 경우보다 약간만 복잡합니다.  설치 단계에서는 다음과 같이 두 가지 매니페스트가 필요합니다.  
  
-   COM 응용 프로그램에는 관리되는 구성 요소를 식별하기 위한 Win32 스타일의 응용 프로그램 매니페스트가 있어야 합니다.  
  
-   .NET Framework 기반 구성 요소에는 런타임에 필요한 활성화 정보를 포함하는 구성 요소 매니페스트가 있어야 합니다.  
  
 이 항목에서는 응용 프로그램 매니페스트를 응용 프로그램과 연결하는 방법, 구성 요소 매니페스트를 구성 요소와 연결하는 방법 및 구성 요소 매니페스트를 어셈블리에 포함하는 방법에 대해 설명합니다.  
  
### 응용 프로그램 매니페스트를 만들려면  
  
1.  XML 편집기를 사용하여 하나 이상의 관리되는 구성 요소와 상호 운용하는 COM 응용 프로그램 소유의 응용 프로그램 매니페스트를 만들거나 수정합니다.  
  
2.  파일의 처음에 다음과 같은 표준 헤더를 삽입합니다.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     매니페스트 요소 및 특성에 대한 내용을 보려면 MSDN Library에서 "응용 프로그램 매니페스트 참조"를 검색하십시오.  
  
3.  매니페스트의 소유자를 식별합니다.  다음 예제에서는 `myComApp` 버전 1이 매니페스트 파일을 소유합니다.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="msil"   
      />  
    ```  
  
4.  종속 어셈블리를 식별합니다.  다음 예제에서는 `myComApp`가 `myManagedComp`에 종속됩니다.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="x86"   
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myManagedComp"   
                        version="6.0.0.0"   
                        processorArchitecture="X86"   
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5.  매니페스트 파일을 저장하고 이름을 지정합니다.  응용 프로그램 매니페스트의 이름은 어셈블리 실행 파일 이름 뒤에 .manifest 확장명을 붙인 것입니다.  예를 들어, myComApp.exe의 응용 프로그램 매니페스트 파일 이름은 myComApp.exe.manifest입니다.  
  
 COM 응용 프로그램과 같은 디렉터리에 응용 프로그램 매니페스트를 설치할 수 있습니다.  또는, 응용 프로그램 매니페스트를 응용 프로그램의 .exe 파일에 리소스로 추가할 수 있습니다.  자세한 내용을 보려면 MSDN Library에서 "Side\-by\-side 어셈블리"를 검색하십시오.  
  
#### 구성 요소 매니페스트를 만들려면  
  
1.  XML 편집기를 사용하여 관리되는 어셈블리를 설명하는 구성 요소 매니페스트를 만듭니다.  
  
2.  파일의 처음에 다음과 같은 표준 헤더를 삽입합니다.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3.  파일의 소유자를 식별합니다.  응용 프로그램 매니페스트 파일에 있는 `<dependentAssembly>` 요소의 `<assemblyIdentity>` 요소는 구성 요소 매니페스트에 있는 해당 요소와 일치해야 합니다.  다음 예제에서는 `myManagedComp` 버전 1.2.3.4가 매니페스트 파일을 소유합니다.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4.  어셈블리에 있는 각 클래스를 식별합니다.  관리되는 어셈블리에 있는 각 클래스를 고유하게 식별하려면 `<clrClass>` 요소를 사용합니다.  `<assembly>` 요소의 하위 요소인 이 요소에는 다음 표에 설명된 특성이 있습니다.  
  
    |특성|설명|필수|  
    |--------|--------|--------|  
    |`clsid`|활성화할 클래스를 지정하는 식별자입니다.|예|  
    |`description`|사용자에게 구성 요소에 대해 알려 주는 문자열입니다.  빈 문자열이 기본값입니다.|아니요|  
    |`name`|관리되는 클래스를 나타내는 문자열입니다.|예|  
    |`progid`|런타임에 바인딩된 활성화에 사용되는 식별자입니다.|아니요|  
    |`threadingModel`|COM 스레딩 모델입니다. "Both"가 기본값입니다.|아니요|  
    |`runtimeVersion`|사용할 CLR\(공용 언어 런타임\) 버전을 지정합니다.  이 특성을 지정하지 않은 경우 CLR을 아직 로드하지 않았으면 CLR 4 이전 버전 중 가장 최근에 설치한 CLR을 사용하여 구성 요소가 로드됩니다.  v1.0.3705, v1.1.4322 또는 v2.0.50727을 지정하면 CLR 4 이전 버전 중 가장 최근에 설치한 CLR 버전\(일반적으로 v2.0.50727\)으로 버전이 자동 롤포워드됩니다.  다른 버전의 CLR을 이미 로드한 경우 지정된 버전을 In\-Process Side\-by\-Side 방식으로 로드할 수 있으면 지정된 버전이 로드되고, 그렇지 않으면 이미 로드한 CLR이 사용됩니다.  이 경우 로드 문제가 발생할 수도 있습니다.|아니요|  
    |`tlbid`|클래스에 대한 형식 정보가 들어 있는 형식 라이브러리의 식별자입니다.|아니요|  
  
     모든 특성 태그는 대\/소문자가 구분됩니다.  OLE\/COM ObjectViewer\(Oleview.exe\)에서 해당 어셈블리에 대해 내보낸 형식 라이브러리를 열어 보면 CLSID, ProgID, 스레딩 모델 및 런타임 버전을 확인할 수 있습니다.  
  
     다음 구성 요소 매니페스트에서는 `testClass1` 및 `testClass2`라는 두 개의 클래스를 식별합니다.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4" />  
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5.  매니페스트 파일을 저장하고 이름을 지정합니다.  구성 요소 매니페스트의 이름은 어셈블리 라이브러리 이름에 .manifest 확장명을 붙인 것입니다.  예를 들어, myManagedComp.dll은 myManagedComp.manifest가 됩니다.  
  
 구성 요소 매니페스트는 어셈블리에 리소스로 포함시켜야 합니다.  
  
#### 구성 요소 매니페스트를 관리되는 어셈블리에 포함시키려면  
  
1.  다음 문을 포함하는 리소스 스크립트를 만듭니다.  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     이 문에서 `myManagedComp.manifest`는 포함할 구성 요소 매니페스트의 이름입니다.  이 예제의 경우 스크립트 파일 이름은 `myresource.rc`입니다.  
  
2.  Microsoft Windows Resource Compiler\(Rc.exe\)를 사용하여 스크립트를 컴파일합니다.  명령 프롬프트에 다음 명령을 입력합니다.  
  
     `rc myresource.rc`  
  
     Rc.exe는 `myresource.res` 리소스 파일을 생성합니다.  
  
3.  어셈블리의 소스 파일을 다시 컴파일하고 다음과 같이 **\/win32res** 옵션을 사용하여 리소스 파일을 지정합니다.  
  
    ```  
    /win32res:myresource.res  
    ```  
  
     `myresource.res`는 포함할 리소스가 들어 있는 리소스 파일의 이름입니다.  
  
## 참고 항목  
 [등록이 필요 없는 COM Interop](../../../docs/framework/interop/registration-free-com-interop.md)   
 [Requirements for Registration\-Free COM Interop](http://msdn.microsoft.com/ko-kr/0c43bc57-eecf-4e6c-8114-490141cce4da)   
 [Configuring COM Components for Registration\-Free Activation](http://msdn.microsoft.com/ko-kr/bfe9b02f-d964-4784-960e-a1f94692fbfe)   
 [.NET 기반 구성 요소의 등록이 필요 없는 활성화: 연습](http://go.microsoft.com/fwlink/?LinkId=158812)