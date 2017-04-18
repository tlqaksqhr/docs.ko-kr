---
title: "방법: WPF 응용 프로그램에 시작 화면 추가 | Microsoft Docs"
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
  - "시작 화면[WPF]"
  - "SplashScreen 클래스[WPF]"
  - "시작 창[WPF]"
  - "WPF, 시작 화면"
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: WPF 응용 프로그램에 시작 화면 추가
이 항목에서는 WPF\(Windows Presentation Foundation\) 응용 프로그램에 시작 창 또는 *시작 화면*을 추가하는 방법을 보여 줍니다.  
  
### 기존 이미지를 시작 화면으로 추가하려면  
  
1.  시작 화면으로 사용할 이미지를 만들거나 찾습니다.  WIC\(Windows Imaging Component\)에서 지원하는 모든 이미지 형식을 사용할 수 있습니다.  예를 들어 BMP, GIF, JPEG, PNG 또는 TIFF 형식을 사용할 수 있습니다.  
  
2.  이미지 파일을 WPF 응용 프로그램 프로젝트에 추가합니다.  자세한 내용은 [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/ko-kr/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)를 참조하십시오.  
  
3.  솔루션 탐색기에서 이미지를 선택합니다.  
  
4.  속성 창에서 **빌드 작업** 속성의 드롭다운 화살표를 클릭합니다.  
  
5.  드롭다운 목록에서 **SplashScreen**을 선택합니다.  
  
    > [!NOTE]
    >  **SplashScreen** 옵션이 보이지 않으면 현재 [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 이상의 버전을 사용하고 있는지 확인하십시오.  
  
6.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
     화면 중앙에 시작 화면 이미지가 나타났다가 주 응용 프로그램 창이 나타나면 사라집니다.  
  
### 응용 프로그램에서 시작 화면을 제거하려면  
  
1.  솔루션 탐색기에서 시작 화면 이미지를 선택합니다.  
  
2.  속성 창에서 **빌드 작업**을 **없음**으로 설정합니다.  
  
### 응용 프로그램에서 시작 화면을 제거하려면  
  
-   솔루션 탐색기에서 시작 화면 이미지를 삭제합니다.  
  
-   시작 화면 이미지를 프로젝트에서 제외합니다.  
  
## 참고 항목  
 <xref:System.Windows.SplashScreen>   
 [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/ko-kr/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)