---
title: '방법: IIS 5.0 및 IIS 6.0을 구성하여 WPF 응용 프로그램 배포'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MIME types [WPF], registering
- adjusting content expiration setting [WPF]
- registering file extensions [WPF]
- deploying applications [WPF]
- applications [WPF], deploying
- Web servers [WPF], configuring to deploy WPF applications
- configuring Web servers to deploy WPF applications [WPF]
- content expiration setting [WPF], adjusting
- file extensions [WPF], registering
- registering MIME types [WPF]
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: edc4bc985f7117dc66d29053d62a283d67b01a85
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a>방법: IIS 5.0 및 IIS 6.0을 구성하여 WPF 응용 프로그램 배포
적절한 [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] 형식으로 구성된 경우 대부분의 웹 서버에서 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 배포할 수 있습니다. 기본적으로 [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)]는 이러한 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식으로 구성되지만 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]과 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]은 아닙니다.  
  
 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 배포하도록 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]과 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]을 구성하는 방법을 설명합니다.  
  
  
> [!NOTE]
>  확인할 수 있습니다는 *UserAgent* 시스템에.NET Framework가 설치 되어 있는지 확인 하려면 레지스트리에서 문자열입니다. 자세한 내용 및 검사 하는 스크립트는 *UserAgent* .NET Framework 시스템에 설치 되어 있는지 확인 하려면 참조 문자열 [검색 the.NET Framework 3.0이 설치 되어 있는지](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)합니다.  
  
<a name="content_expiration"></a>   
## <a name="adjust-the-content-expiration-setting"></a>콘텐츠 만료 설정 조정  
 콘텐츠 만료 설정을 1분으로 조정할 수 있습니다. 다음 절차에서는 [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)]로 이 작업을 수행하는 방법을 간략하게 설명합니다.  
  
1.  **시작** 메뉴를 클릭하고 **관리 도구**를 가리킨 후 **IIS(인터넷 정보 서비스) 관리자**를 클릭합니다. 명령줄에서도 “%SystemRoot%\system32\inetsrv\iis.msc”로 이 응용 프로그램을 시작할 수 있습니다.  
  
2.  **기본 웹 사이트** 노드가 표시될 때까지 [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] 트리를 펼칩니다.  
  
3.  **기본 웹 사이트**를 마우스 오른쪽 단추로 클릭하고 컨텍스트 메뉴에서 **속성**을 선택합니다.  
  
4.  **HTTP 헤더** 탭을 선택하고 “콘텐츠 만료 사용”을 클릭합니다.  
  
5.  1분 후에 만료하도록 콘텐츠를 설정합니다.  
  
<a name="register_mime_types"></a>   
## <a name="register-mime-types-and-file-extensions"></a>MIME 형식과 파일 확장명 등록  
 클라이언트의 시스템에서 브라우저가 올바른 처리기를 로드할 수 있도록 여러 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식과 파일 확장명을 등록해야 합니다. 다음 형식을 추가해야 합니다.  
  
|확장명|MIME 형식|  
|---------------|---------------|  
|.manifest|application/manifest|  
|.xaml|application/xaml+xml|  
|.application|application/x-ms-application|  
|.xbap|application/x-ms-xbap|  
|.deploy|application/octet-stream|  
|.xps|application/vnd.ms-xpsdocument|  
  
> [!NOTE]
>  클라이언트 시스템에서 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식 또는 파일 확장명을 등록하지 않아도 됩니다. Microsoft.NET Framework를 설치할 때 자동으로 등록 된 합니다.  
  
 다음 Microsoft Visual Basic Scripting Edition (VBScript) 예제에는 자동으로 필요한 추가 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 유형를 [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)]합니다. 스크립트를 사용하려면 서버에서 .vbs 파일을 코드에 복사합니다. 그런 다음 명령줄에서 파일을 실행하거나 [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)]에서 파일을 두 번 클릭하여 스크립트를 실행합니다.  
  
```  
' This script adds the necessary Windows Presentation Foundation MIME types   
' to an IIS Server.  
' To use this script, just double-click or execute it from a command line.  
' Running this script multiple times results in multiple entries in the IIS MimeMap.  
  
Dim MimeMapObj, MimeMapArray, MimeTypesToAddArray, WshShell, oExec  
Const ADS_PROPERTY_UPDATE = 2   
  
' Set the MIME types to be added  
MimeTypesToAddArray = Array(".manifest", "application/manifest", ".xaml", _  
    "application/xaml+xml", ".application", "application/x-ms-application", _  
    ".deploy", "application/octet-stream", ".xbap", "application/x-ms-xbap", _  
    ".xps", "application/vnd.ms-xpsdocument")   
  
' Get the mimemap object   
Set MimeMapObj = GetObject("IIS://LocalHost/MimeMap")  
  
' Call AddMimeType for every pair of extension/MIME type  
For counter = 0 to UBound(MimeTypesToAddArray) Step 2  
    AddMimeType MimeTypesToAddArray(counter), MimeTypesToAddArray(counter+1)  
Next  
  
' Create a Shell object  
Set WshShell = CreateObject("WScript.Shell")  
  
' Stop and Start the IIS Service  
Set oExec = WshShell.Exec("net stop w3svc")  
Do While oExec.Status = 0  
    WScript.Sleep 100  
Loop  
  
Set oExec = WshShell.Exec("net start w3svc")  
Do While oExec.Status = 0  
    WScript.Sleep 100  
Loop  
  
Set oExec = Nothing  
  
' Report status to user  
WScript.Echo "Windows Presentation Foundation MIME types have been registered."  
  
' AddMimeType Sub  
Sub AddMimeType (Ext, MType)  
  
    ' Get the mappings from the MimeMap property.   
    MimeMapArray = MimeMapObj.GetEx("MimeMap")   
  
    ' Add a new mapping.   
    i = UBound(MimeMapArray) + 1   
    Redim Preserve MimeMapArray(i)   
    Set MimeMapArray(i) = CreateObject("MimeMap")   
    MimeMapArray(i).Extension = Ext   
    MimeMapArray(i).MimeType = MType   
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray  
    MimeMapObj.SetInfo  
  
End Sub  
```  
  
> [!NOTE]
>  이 스크립트를 여러 번 실행하면 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] 메타베이스에서 여러 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 맵 항목을 만듭니다.  
  
 이 스크립트는 실행하고 나면 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)]에서 추가 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식이 표시되지 않을 수 있습니다. 그러나 이러한 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식이 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] 메타베이스에 추가되었습니다. 다음 스크립트는 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] 메타베이스의 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식을 모두 표시합니다.  
  
```  
' This script lists the MIME types for an IIS Server.  
' To use this script, just double-click or execute it from a command line   
' by calling cscript.exe  
  
dim mimeMapEntry, allMimeMaps  
  
' Get the mimemap object.  
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")  
allMimeMaps = mimeMapEntry.GetEx("MimeMap")  
  
' Display the mappings in the table.  
For Each mimeMap In allMimeMaps  
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")  
Next  
```  
  
 스크립트를 `.vbs` 파일로 저장하고(예: `DiscoverIISMimeTypes.vbs`) 다음 명령을 사용하여 명령 프롬프트에서 실행합니다.  
  
 `cscript DiscoverIISMimeTypes.vbs`
