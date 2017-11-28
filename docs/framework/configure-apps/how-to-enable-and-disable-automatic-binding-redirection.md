---
title: "방법: 자동 바인딩 리디렉션 사용 설정 및 해제"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 83b004934c303c95bdc4e6edb6031a86e2b1a6ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>방법: 자동 바인딩 리디렉션 사용 설정 및 해제
[!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)]부터 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]을 대상으로 하는 응용 프로그램을 컴파일할 때, 바인딩 리디렉션이 어셈블리 통합을 재정의하기 위한 응용 프로그램 구성 파일에 자동으로 추가될 수 있습니다. 수동으로 바인딩 리디렉션을 응용 프로그램의 구성 파일에 지정할 지라도 응용 프로그램 또는 해당 구성 요소가 동일 어셈블리의 두 개 이상의 버전을 참조할 경우 바인딩 리디렉션을 추가합니다. 자동 바인딩 리디렉션 기능은 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]을 적용 대상으로 하는 전통적인 데스크톱 응용 프로그램 및 웹 응용 프로그램에 영향을 줍니다. 웹 응용 프로그램에서는 동작이 약간 달라집니다. 이전 버전의 .NET Framework를 대상으로 하는 기존 응용 프로그램이 있는 경우 자동 바인딩 리디렉션을 사용할 수 있으며, 수동으로 작성되는 바인딩 리디렉션을 유지하려는 경우에는 이 기능을 비활성화할 수 있습니다.  
  
## <a name="disabling-automatic-binding-redirects-in-desktop-apps"></a>데스크톱 앱에서 자동 바인딩 리디렉션 사용 안 함  
 자동 바인딩 리디렉션은 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]을 대상으로 하는 기존 데스크톱 앱에 대해 기본적으로 사용하도록 설정됩니다. 응용 프로그램이 컴파일되고 그렇지 않으면 발생할 수 있는 어셈블리 통합을 재정의할 때 바인딩 리디렉션이 출력 구성(app.config) 파일에 추가됩니다. 소스 app.config 파일은 수정되지 않습니다. 응용 프로그램에 대한 프로젝트 파일을 수정하여 이 기능을 비활성화할 수 있습니다.  
  
#### <a name="to-disable-automatic-binding-redirects"></a>자동 바인딩 리디렉션을 비활성화하려면  
  
1.  Visual Studio에서 프로젝트를 선택 **솔루션 탐색기**를 선택한 후 **파일 탐색기에서 폴더 열기** 바로 가기 메뉴에서.  
  
2.  파일 탐색기에서 프로젝트(.csproj 또는 .vbproj) 파일을 찾아서 메모장에서 엽니다.  
  
3.  프로젝트 파일에서 다음 속성 항목을 찾습니다.  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
4.  `true`를 `false`로 변경합니다.  
  
     `<AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>`  
  
## <a name="enabling-automatic-binding-redirects-manually"></a>수동으로 자동 바인딩 리디렉션 사용  
 이전 버전의 .NET Framework를 대상으로 하는 기존 앱에서나, 리디렉션을 추가하라는 메시지가 자동으로 나타나지 않는 경우에 자동 바인딩 리디렉션을 사용하도록 설정할 수 있습니다. 최신 버전의 Framework를 대상으로 하지만 리디렉션을 추가하라는 메시지가 자동으로 나타나지 않는 경우 어셈블리를 다시 매핑하도록 제안하는 빌드 출력이 표시될 것입니다.  
  
#### <a name="to-manually-add-an-automatic-binding-redirect-property"></a>수동으로 자동 바인딩 리디렉션 속성을 추가하려면  
  
1.  Visual Studio에서 프로젝트를 선택 **솔루션 탐색기**를 선택한 후 **파일 탐색기에서 폴더 열기** 바로 가기 메뉴에서.  
  
2.  파일 탐색기에서 프로젝트(.csproj 또는 .vbproj) 파일을 찾아서 메모장에서 엽니다.  
  
3.  다음 요소를 첫 번째 구성 속성 그룹에 추가 (아래에서 \<PropertyGroup > 태그):  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
     다음은 요소가 삽입된 예제 프로젝트 파일을 보여 줍니다.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == ''     ">Debug</Configuration>  
        <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
        <ProjectGuid>{123334}</ProjectGuid>  
        ...  
        <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>  
      </PropertyGroup>  
    ...  
    </Project>  
    ```  
  
4.  응용 프로그램을 컴파일합니다.  
  
## <a name="enabling-automatic-binding-redirects-in-web-apps"></a>웹 응용 프로그램에서 자동 바인딩 리디렉션 사용  
 자동 바인딩 리디렉션은 웹 응용 프로그램마다 다르게 구현됩니다. 웹 응용 프로그램에 대한 원본 구성(web.config) 파일을 수정해야 하기 때문에 구성 파일에 바인딩 리디렉션은 자동으로 추가되지 않습니다. 하지만 Visual Studio는 바인딩 충돌을 경고하고 충돌 해결을 위해 바인딩 리디렉션을 추가할 수 있습니다. 항상 바인딩 리디렉션을 추가하려고 하기 때문에 웹 응용 프로그램에서 이 기능을 명시적으로 비활성화할 필요는 없습니다.  
  
#### <a name="to-add-binding-redirects-to-a-webconfig-file"></a>web.config 파일에 바인딩 리디렉션을 추가하려면  
  
1.  Visual Studio에서 응용 프로그램을 컴파일하고 빌드 경고를 확인합니다.  
  
     ![어셈블리 참고 충돌에 대 한 경고를 빌드](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")  
  
2.  어셈블리 바인딩 충돌이 있을 경우 경고가 나타납니다. 경고를 두 번 클릭합니다. (키보드: 경고 및 키를 눌러 선택 **Enter**.)  
  
     필요한 바인딩 리디렉션을 소스 web.config 파일에 자동으로 추가할 수 있는 대화 상자가 나타납니다.  
  
     ![바인딩 리디렉션 권한 대화 상자](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")  
  
## <a name="see-also"></a>참고 항목  
 [\<bindingRedirect > 요소](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
 [어셈블리 버전 리디렉션](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
