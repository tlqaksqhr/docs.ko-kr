---
title: "방법: IIS 5.0 및 IIS 6.0을 구성하여 WPF 응용 프로그램 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "콘텐츠 만료 설정 조정"
  - "응용 프로그램, 배포"
  - "WPF 응용 프로그램을 배포할 웹 서버 구성"
  - "콘텐츠 만료 설정, 조정"
  - "응용 프로그램 배포"
  - "파일 확장명, 등록"
  - "MIME 형식, 등록"
  - "파일 확장명 등록"
  - "MIME 형식 등록"
  - "웹 서버, WPF 응용 프로그램 배포를 위한 구성"
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: IIS 5.0 및 IIS 6.0을 구성하여 WPF 응용 프로그램 배포
대부분의 웹 서버에서는 [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] 형식만 적절하게 구성되어 있으면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 배포할 수 있습니다.  기본적으로 [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)]에는 이러한 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식이 구성되어 있지만 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 및 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]의 경우에는 그렇지 않습니다.  
  
 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 배포할 수 있도록 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 및 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]을 구성하는 방법을 설명합니다.  
  
   
  
> [!NOTE]
>  레지스트리에서 *UserAgent* 문자열을 검사하여 시스템에 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]이 설치되어 있는지 확인할 수 있습니다.  자세한 내용 및 *UserAgent* 문자열을 검사하여 시스템에 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]이 설치되었는지 확인하는 스크립트를 보려면 [.NET Framework 3.0 설치 여부 확인](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)을 참조하십시오.  
  
<a name="content_expiration"></a>   
## 콘텐츠 만료 설정 조정  
 콘텐츠 만료 설정은 1분으로 조정해야 합니다.  다음 절차에서는 [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)]에서 이러한 작업을 수행하는 방법을 설명합니다.  
  
1.  **시작** 메뉴를 클릭하고 **관리 도구**를 가리킨 다음 **인터넷 정보 서비스\(IIS\) 관리**를 클릭합니다.  명령줄에서 "%SystemRoot%\\system32\\inetsrv\\iis.msc"를 입력하여 이 응용 프로그램을 시작할 수도 있습니다.  
  
2.  **기본 웹 사이트** 노드가 보일 때까지 [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] 트리를 확장합니다.  
  
3.  **기본 웹 사이트**를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **등록 정보**를 선택합니다.  
  
4.  **HTTP 헤더** 탭을 선택하고 "콘텐츠 만료 지정"을 클릭합니다.  
  
5.  콘텐츠가 1분 후 만료되도록 설정합니다.  
  
<a name="register_mime_types"></a>   
## MIME 형식 및 파일 확장명 등록  
 클라이언트 시스템의 브라우저에서 올바른 처리기를 로드할 수 있으려면 몇 가지 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식과 파일 확장명을 등록해야 합니다.  추가해야 할 형식은 다음과 같습니다.  
  
|확장명|MIME 형식|  
|---------|-------------|  
|.manifest|application\/manifest|  
|.xaml|application\/xaml\+xml|  
|.application|application\/x\-ms\-application|  
|.xbap|application\/x\-ms\-xbap|  
|.deploy|application\/octet\-stream|  
|.xps|application\/vnd.ms\-xpsdocument|  
  
> [!NOTE]
>  클라이언트 시스템에는 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식이나 파일 확장명을 등록하지 않아도 됩니다.  이러한 정보는 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]을 설치할 때 자동으로 등록됩니다.  
  
 다음 [!INCLUDE[TLA#tla_visualbscrpt](../../../../includes/tlasharptla-visualbscrpt-md.md)] 샘플은 필요한 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식을 [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)]에 자동으로 추가합니다.  이 스크립트를 사용하려면 서버에 있는 .vbs 파일에 코드를 복사한 후  명령줄에서 파일을 실행하거나 [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)]에서 파일을 두 번 클릭하여 스크립트를 실행합니다.  
  
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
>  이 스크립트를 여러 번 실행하면 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] 메타베이스에 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 맵 엔트리가 여러 개 만들어집니다.  
  
 이 스크립트를 실행한 후 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)]에 추가 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식이 보이지 않을 수 있습니다.  그러나 이러한 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식은 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] 메타베이스에 추가되었습니다.  다음 스크립트는 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] 메타베이스에 있는 모든 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식을 표시합니다.  
  
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
  
 스크립트를 `.vbs` 파일\(예: `DiscoverIISMimeTypes.vbs`\)로 저장한 후 다음 명령을 사용하여 명령 프롬프트에서 실행합니다.  
  
 `cscript DiscoverIISMimeTypes.vbs`