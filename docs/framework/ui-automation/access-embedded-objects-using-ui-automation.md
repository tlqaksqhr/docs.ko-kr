---
title: "Access Embedded Objects Using UI Automation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "embedded objects, accessing"
  - "accessing embedded objects"
  - "UI Automation, accessing embedded objects"
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
caps.latest.revision: 17
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 17
---
# Access Embedded Objects Using UI Automation
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]을 텍스트 컨트롤의 내용에 포함된 개체를 노출하는 데 사용하는 방법을 보여줍니다.  
  
> [!NOTE]
>  포함된 개체에는 이미지, 하이퍼링크, 단추, 테이블 또는 ActiveX 컨트롤이 있습니다.  
  
 포함된 개체는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 텍스트 공급자의 자식 항목으로 간주됩니다. 이를 통해 포함된 개체가 기타 모든 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 요소와 동일한 UI 자동화 트리 구조를 통해 노출될 수 있습니다. 따라서 포함된 개체 컨트롤 형식에 일반적으로 필요한 컨트롤 패턴을 통해 기능이 노출됩니다\(예: 하이퍼링크는 텍스트를 기반으로 하므로 <xref:System.Windows.Automation.TextPattern>을 지원함\).  
  
 ![텍스트 컨테이너의 포함된 개체](../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA\_TextPattern\_EmbeddedObjects")  
텍스트 내용이 있는 샘플 문서\("알고 계신가요?"\) 및 두 개의 포함된 개체\(고래 및 텍스트 하이퍼링크의 그림\)는 코드 예제에 대한 대상으로 사용됩니다.  
  
## 예제  
 다음 코드 예제는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 텍스트 공급자에서 포함된 개체의 컬렉션을 검색하는 방법을 보여줍니다. 소개 부분에 제공된 샘플 문서의 경우 두 개의 개체가 반환됩니다\(이미지 요소 및 텍스트 요소\).  
  
> [!NOTE]
>  이미지 요소에는 해당 이미지를 설명하는 연관된 내장 텍스트가 있어야 하며, 일반적으로 <xref:System.Windows.Automation.AutomationElement.NameProperty>에 있습니다\(예: "파란색 고래"\). 하지만 이미지 개체에 걸쳐 있는 텍스트 범위를 가져오면 텍스트 스트림에 이미지 또는 설명 텍스트가 반환되지 않습니다.  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## 예제  
 다음 코드 예제는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 텍스트 공급자 내에 포함된 개체에서 텍스트 범위를 가져오는 방법을 보여줍니다. 검색된 텍스트 범위는 빈 범위로서 시작되는 끝점 앞에 "… ocean.\(space\)"가 오고 끝나는 끝점 뒤에 닫는 "."가 와서 포함된 하이퍼링크를 나타냅니다\(소개 부분에 제공된 이미지 참조\). 검색된 범위가 비어 있는 범위라 해도, 0이 아닌 범위이기 때문에 중복 제거 범위로 간주되지 않습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Automation.TextPattern>은 하이퍼링크와 같이 텍스트를 기반으로 하는 포함된 개체를 검색할 수 있지만, 보조 <xref:System.Windows.Automation.TextPattern>은 포함된 개체에서 가져와야 전체 기능을 노출할 수 있습니다.  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## 참고 항목  
 [UI Automation TextPattern Overview](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)   
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Add Content to a Text Box Using UI Automation](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)   
 [Find and Highlight Text Using UI Automation](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)