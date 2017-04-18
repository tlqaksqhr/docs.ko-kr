---
title: "응용 프로그램 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# 응용 프로그램 구성
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 .NET 구성 시스템이 사용되며 컴퓨터와 응용 프로그램 범위 모두에서 서비스를 구성할 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 정의한 구성 설정은 `<system.serviceModel>` 섹션 그룹에 있습니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 구성하는 방법에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 다음 항목을 참조하십시오.  
  
-   [서비스 구성](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 응용 프로그램에서 정의한 구성 설정은 `<appSettings>` 섹션 그룹에 정의되어 있습니다..NET 구성 파일의 응용 프로그램 설정에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [\<appSettings\>](http://go.microsoft.com/fwlink/?LinkId=95159)\(영문 페이지일 수 있음\)를 참조하십시오.  
  
## Configuration Editor 사용  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [Configuration Editor 도구\(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)를 사용하면 관리자와 개발자가 그래픽 사용자 인터페이스를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 구성 설정을 만들고 수정할 수 있습니다.이 도구를 사용하면 XML 구성 파일을 직접 수정하지 않고도 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 바인딩, 동작, 서비스 및 진단에 대한 설정을 관리할 수 있습니다.  
  
## Visual Studio에서 구성 파일 편집  
 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 프로젝트의 구성 파일을 편집하려면 **솔루션 탐색기**에서 구성 파일을 마우스 오른쪽 단추로 클릭한 다음 **WCF 구성 편집** 상황에 맞는 메뉴 항목을 선택합니다.그러면 [Configuration Editor 도구\(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)가 시작됩니다.  
  
> [!NOTE]
>  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]의 **솔루션 탐색기**에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 웹 서비스 프로젝트의 구성 파일을 마우스 오른쪽 단추로 클릭하여 편집하는 경우 **Edit WCF Configuration** 상황에 맞는 메뉴 항목이 표시되지 않습니다.이 문제를 해결하려면 **도구** 메뉴를 클릭하고 **WCF SvcConfigEditor**를 선택합니다.그런 다음 구성 파일을 마우스 오른쪽 단추로 클릭하고 **Edit WCF Configuration** 상황에 맞는 메뉴 항목을 사용할 수 있습니다.  
  
## 참고 항목  
 [Configuration Editor 도구\(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)   
 [서비스 구성](../../../../docs/framework/wcf/configuring-services.md)   
 [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)