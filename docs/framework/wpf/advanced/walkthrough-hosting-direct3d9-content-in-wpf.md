---
title: "연습: WPF에서 Direct3D9 콘텐츠 호스팅 | Microsoft Docs"
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
  - "Direct3D9[WPF 상호 운용성], Direct3D9 콘텐츠 호스팅"
  - "WPF, Direct3D9 콘텐츠 호스팅"
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 연습: WPF에서 Direct3D9 콘텐츠 호스팅
이 연습에서는 WPF\(Windows Presentation Foundation\) 응용 프로그램에서 Direct3D9 콘텐츠를 호스팅하는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   Direct3D9 콘텐츠를 호스팅할 WPF 프로젝트를 만듭니다.  
  
-   Direct3D9 콘텐츠를 가져옵니다.  
  
-   <xref:System.Windows.Interop.D3DImage> 클래스를 사용하여 Direct3D9 콘텐츠를 표시합니다.  
  
 작업을 마치면 WPF 응용 프로그램에서 Direct3D9 콘텐츠를 호스팅하는 방법을 알 수 있습니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK 9 이상  
  
-   WPF 호환 형식의 Direct3D9 콘텐츠가 포함된 DLL.  자세한 내용은 [WPF 및 Direct3D9 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) 및 [연습: WPF에서 호스팅할 Direct3D9 콘텐츠 만들기](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)를 참조하십시오.  
  
## WPF 프로젝트 만들기  
 첫 번째 단계는 WPF 응용 프로그램의 프로젝트를 만드는 것입니다.  
  
#### WPF 프로젝트를 만들려면  
  
-   Visual C\#에서 `D3DHost`라는 새 WPF 응용 프로그램 프로젝트를 만듭니다.  자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/ko-kr/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하십시오.  
  
     [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]에 MainWindow.xaml이 열립니다.  
  
## Direct3D9 콘텐츠 가져오기  
 `DllImport` 특성을 사용하여 관리되지 않는 DLL에서 Direct3D9 콘텐츠를 가져옵니다.  
  
#### Direct3D9 콘텐츠를 가져오려면  
  
1.  코드 편집기에서 MainWindow.xaml.cs를 엽니다.  
  
2.  자동으로 생성된 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## Direct3D9 콘텐츠 호스팅  
 마지막으로 <xref:System.Windows.Interop.D3DImage> 클래스를 사용하여 Direct3D9 콘텐츠를 호스팅합니다.  
  
#### Direct3D9 콘텐츠를 호스팅하려면  
  
1.  MainWindow.xaml에서 자동으로 생성된 XAML을 다음 XAML로 바꿉니다.  
  
     [!code-xml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  프로젝트를 빌드합니다.  
  
3.  Direct3D9 콘텐츠가 포함된 DLL을 bin\/Debug 폴더에 복사합니다.  
  
4.  F5 키를 눌러 프로젝트를 실행합니다.  
  
     WPF 응용 프로그램에 Direct3D9 콘텐츠가 나타납니다.  
  
## 참고 항목  
 <xref:System.Windows.Interop.D3DImage>   
 [Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)