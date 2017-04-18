---
title: "방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 그룹화"
  - "Panel 컨트롤[Windows Forms], 컨트롤 그룹화"
  - "Windows Forms 컨트롤, 그룹화"
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화
Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 다른 컨트롤을 그룹화하는 데 사용됩니다.  컨트롤을 그룹화하는 데는 세 가지 이유가 있습니다.  첫째, 서로 관련된 폼 요소를 시각적으로 그룹화하여 사용자에게 명확한 인터페이스를 제공합니다. 둘째, 라디오 단추 등을 프로그래밍 방식으로 그룹화합니다. 셋째, 디자인 타임에서 여러 컨트롤을 한 단위로 이동합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 컨트롤 그룹을 만들려면  
  
1.  도구 상자의 **Windows Forms** 탭에 있는 <xref:System.Windows.Forms.Panel> 컨트롤을 폼에 끌어 옵니다.  
  
2.  다른 컨트롤을 패널에 추가하고 해당 패널 안에서 각 컨트롤을 그립니다.  
  
     기존의 컨트롤을 패널에 넣으려면 모든 컨트롤을 선택하고 클립보드에 잘라낸 다음 <xref:System.Windows.Forms.Panel> 컨트롤을 선택하여 패널에 붙여넣습니다.  패널에 직접 끌어 올 수도 있습니다.  
  
3.  필요에 따라 패널에 테두리를 추가하려면 <xref:System.Windows.Forms.BorderStyle> 속성을 설정합니다.  <xref:System.Windows.Forms.BorderStyle>, <xref:System.Windows.Forms.BorderStyle> 및 <xref:System.Windows.Forms.BorderStyle> 중 하나를 선택할 수 있습니다.  
  
## 참고 항목  
 [Panel 컨트롤](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Panel 컨트롤 개요](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [방법: 패널의 배경 설정](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)