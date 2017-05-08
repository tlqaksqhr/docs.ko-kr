---
title: "방법: 설치된 WPF 버전 확인 | Microsoft Docs"
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
  - "버전, 찾기"
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# 방법: 설치된 WPF 버전 확인
현재 설치되어 있는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 버전에 대한 버전 번호는 **레지스트리**에 있습니다.  
  
 버전 번호를 찾으려면  
  
1.  **시작** 메뉴에서 **실행**을 클릭합니다.  
  
2.  **열기**에서 **regedit.exe**를 입력합니다.  
  
3.  다음 키를 엽니다.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 버전 번호는 **Version** 값에 저장되어 있습니다.