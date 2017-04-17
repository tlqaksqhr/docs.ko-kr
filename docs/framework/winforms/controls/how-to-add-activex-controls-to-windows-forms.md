---
title: "방법: Windows Forms에 ActiveX 컨트롤 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ActiveX 컨트롤[Windows Forms], 추가"
  - "폼, ActiveX 컨트롤 추가"
  - "Windows Forms 컨트롤, ActiveX 컨트롤"
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: Windows Forms에 ActiveX 컨트롤 추가
Windows Forms 디자이너는 Windows Forms 컨트롤을 수용하는 데 최적화되어 있지만 Windows Forms에 ActiveX 컨트롤을 넣을 수도 있습니다.  
  
> [!CAUTION]
>  Windows Forms에 ActiveX 컨트롤을 추가하면 Windows Forms의 성능이 제한됩니다.  
  
 ActiveX 컨트롤을 폼에 추가하기 전에 먼저 도구 상자에 추가해야 합니다.  자세한 내용은 [도구 상자 사용자 지정 대화 상자, COM 구성 요소](http://msdn.microsoft.com/ko-kr/171333f3-f207-4e02-bbdc-17862556212c)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 클릭합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### Windows Form에 ActiveX 컨트롤을 추가하려면  
  
-   도구 상자에서 해당 컨트롤을 두 번 클릭합니다.  
  
     [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]는 프로젝트의 컨트롤에 대한 모든 참조를 추가합니다.  Windows Forms에서 ActiveX 컨트롤을 사용할 때 유의해야 할 사항에 대한 자세한 내용은 [Windows Form에서 ActiveX 컨트롤을 호스팅할 때 고려 사항](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md)을 참조하십시오.  
  
    > [!NOTE]
    >  Windows Forms ActiveX 컨트롤 가져오기\(AxImp.exe\)에서는 ActiveX 동적 연결 라이브러리를 가져올 때 예상과 다른 형식의 이벤트 인수를 만듭니다.  예를 들어 `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`가 예상되는 경우 AxImp.exe를 실행하면 `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`와 같은 인수가 만들어집니다.  이러한 불규칙성이 있어도 코드는 정상적으로 작동합니다.  자세한 내용은 [Windows Forms ActiveX 컨트롤 가져오기\(Aximp.exe\)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)를 참조하십시오.  
  
## 참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)   
 [Controls and Programmable Objects Compared in Various Languages and Libraries](http://msdn.microsoft.com/ko-kr/021f2a1b-8247-4348-a5ad-e1d9ab23004b)   
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)