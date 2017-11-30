---
title: "사용자 지정 컨트롤 그리기 및 렌더링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: babf3d235f4cca61ad6d0e5fdc4e6b6146c7d060
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="custom-control-painting-and-rendering"></a>사용자 지정 컨트롤 그리기 및 렌더링
사용자 지정 그리기 컨트롤의.NET Framework로 쉽게 수행할 수 있는 여러 복잡 한 작업 중 하나입니다. 사용자 지정 컨트롤을 작성할 때 컨트롤의 그래픽 모양에 대 한 많은 옵션이 있습니다. 상속 되는 컨트롤을 작성 하는 경우는 `Control`, 컨트롤의 그래픽 표현을 렌더링할 수 있는 코드를 제공 해야 합니다. 상속 하 여 사용자 정의 컨트롤을 만드는 경우는 `UserControl`, 상속 되는지 또는 Windows Forms 컨트롤 중 하나에서 있습니다는 표준 그래픽 표시를 재정의 그래픽 코드를 제공 합니다. 구성 요소 컨트롤에 대 한 사용자 지정 렌더링을 제공 하려는 경우는 `UserControl` 제작 하는, 옵션은 더욱 제한 되지만 광범위 한 컨트롤 및 응용 프로그램에 대 한 그래픽 기능을 계속 사용할 수 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [Windows Forms 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 컨트롤을 표시 하는 논리를 프로그래밍 하는 방법을 보여 줍니다.  
  
 [사용자가 그린 컨트롤](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 작성 하 고 컨트롤 렌더링 코드를 재정의 하는 단계에 간략하게 설명 합니다.  
  
 [구성 요소 컨트롤](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 사용자 컨트롤 및 폼의 구성 요소 컨트롤에 대 한 사용자 지정 렌더링 코드를 구현 하는 방법을 설명 합니다.  
  
 [방법: 런타임에 컨트롤 숨기기](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 숨기 거 나 컨트롤을 표시 합니다.  
  
 [방법: 컨트롤에 투명한 배경 적용](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Control.SetStyle%2A> 방법을 불투명, 투명 하 게 또는 반투명 하는 배경색을 만들 수 있습니다.  
  
 [비주얼 스타일을 사용하여 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 비주얼 스타일을 지 원하는 운영 체제에서 사용 하 여 컨트롤을 렌더링 하는 방법을 보여 줍니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.Control>  
 이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.Windows.Forms.UserControl>  
 이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 이 메서드를 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 소개 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Visual Studio의 관점 및 제공 링크에서 자세한 정보를 그래픽 기능입니다.  
  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 사용자 지정 컨트롤을 제작할 수의 종류를 설명 합니다.
