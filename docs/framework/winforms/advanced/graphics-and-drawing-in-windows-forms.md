---
title: "Windows Forms의 그래픽 및 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b2e8bde5d1c2904723282f03a815f17c5cc7622d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Windows Forms의 그래픽 및 그리기
공용 언어 런타임에서는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]라는 Windows [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)](그래픽 장치 인터페이스)의 고급 구현을 사용합니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 통해 그래픽을 만들고, 텍스트를 그리고, 그래픽 이미지를 개체로 조작할 수 있습니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 성능과 사용 편의성을 제공하도록 설계되었습니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용하여 Windows Forms 및 컨트롤에 그래픽 이미지를 렌더링할 수 있습니다. Web Forms에서 직접 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용할 수는 없지만 이미지 웹 서버 컨트롤을 통해 그래픽 이미지를 표시할 수 있습니다.  
  
 이 섹션에는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 프로그래밍의 기본 사항을 소개하는 항목이 있습니다. 포괄적인 참조는 아니지만 이 섹션은 <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Color> 개체에 대한 정보를 포함하며 도형 그리기, 텍스트 그리기 또는 이미지 표시와 같은 작업을 수행하는 방법을 설명합니다. 자세한 내용은 참조 [GDI + 참조](https://msdn.microsoft.com/library/vs/alm/ms533799.aspx)합니다.  
  
 바로 시작하려면 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)을 참조하세요. Windows Forms에서 코드를 사용하여 선, 도형, 텍스트 등을 그리는 방법에 대한 항목이 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [그래픽 개요](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 그래픽 관련 관리되는 클래스를 소개합니다.  
  
 [GDI + 관리 코드 정보](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 관리되는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 클래스에 대한 정보를 제공합니다.  
  
 [관리되는 그래픽 클래스 사용](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 관리되는 클래스를 사용하여 다양한 작업을 완료하는 방법을 보여 줍니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Drawing>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 기본 그래픽 기능에 대한 액세스를 제공합니다.  
  
 <xref:System.Drawing.Drawing2D>  
 고급 2D 및 벡터 그래픽 기능을 제공합니다.  
  
 <xref:System.Drawing.Imaging>  
 고급 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 이미징 기능을 제공합니다.  
  
 <xref:System.Drawing.Text>  
 고급 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 입력 체계 기능을 제공합니다. 이 네임스페이스의 클래스를 통해 글꼴 컬렉션을 만들고 사용할 수 있습니다.  
  
 <xref:System.Drawing.Printing>  
 인쇄 기능을 제공합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [사용자 지정 컨트롤 그리기 및 렌더링](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 컨트롤을 그리기 위한 코드를 제공하는 방법을 자세히 설명합니다.
