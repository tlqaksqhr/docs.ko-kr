---
title: "방법: WPF 응용 프로그램에 시작 화면 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 121cbc1c07ea8f6458df81d861aea3f8e1f91086
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>방법: WPF 응용 프로그램에 시작 화면 추가
이 항목에서는 시작 창에 추가 하는 방법을 보여 줍니다. 또는 *시작 화면*, Windows Presentation Foundation (WPF) 응용 프로그램에 있습니다.  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a>시작 화면으로 기존 이미지를 추가 하려면  
  
1.  만들기 또는 시작 화면에 대 한 사용 하려는 이미지를 찾습니다. Windows Imaging 구성 요소 (WIC)에서 지원 되는 모든 이미지 형식을 사용할 수 있습니다. 예를 들어, BMP, GIF, JPEG, PNG 또는 TIFF 형식을 사용할 수 있습니다.  
  
2.  WPF 응용 프로그램 프로젝트에 이미지 파일을 추가 합니다. 자세한 내용은 참조 [NIB: 방법: 프로젝트에 기존 항목 추가](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)합니다.  
  
3.  솔루션 탐색기에서 이미지를 선택 합니다.  
  
4.  속성 창에서 드롭다운 화살표를 클릭는 **빌드 작업** 속성입니다.  
  
5.  선택 **SplashScreen** 드롭 다운 목록에서 합니다.  
  
    > [!NOTE]
    >  표시 되지 않으면는 **SplashScreen** 옵션을 사용 하 고 있는지 확인 해야 [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 이상.  
  
6.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
     시작 화면 이미지 화면 중앙에 표시 되 고 주 응용 프로그램 창이 표시 되 면 사라집니다.  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>응용 프로그램에서 시작 화면을 제거 하려면  
  
1.  솔루션 탐색기에서 시작 화면 이미지를 선택 합니다.  
  
2.  속성 창에서 설정 된 **빌드 작업** 를 **None**합니다.  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>응용 프로그램에서 시작 화면을 제거 하려면  
  
-   솔루션 탐색기에서 시작 화면 이미지를 삭제 합니다.  
  
-   시작 화면 이미지를 프로젝트에서 제외 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.SplashScreen>  
 [NIB: 방법: 프로젝트에 기존 항목 추가](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
