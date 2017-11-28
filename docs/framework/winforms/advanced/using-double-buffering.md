---
title: "이중 버퍼링 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b5ad51e27c3d31ece1d11831c953023bedba3a97
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="using-double-buffering"></a>이중 버퍼링 사용
복잡 한 그리기 작업을 포함 하는 응용 프로그램에서 깜빡임을 줄이기 위해 이중 버퍼링 된 그래픽을 사용할 수 있습니다. .NET Framework에는 이중 버퍼링에 대 한 기본 제공 지원이 포함 되어 있고 관리 그래픽을 수동으로 렌더링 수 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [이중 버퍼링 그래픽](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 에서는 이중 버퍼링 개념 윤곽선과.NET Framework 지원 합니다.  
  
 [방법: 양식과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 기본 이중 지원.NET Framework의 버퍼링을 사용 하는 방법을 보여 줍니다.  
  
 [방법: 버퍼링된 그래픽 수동 관리](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 응용 프로그램의 이중 버퍼링을 관리 하는 방법을 보여 줍니다.  
  
 [방법: 버퍼링된 그래픽 수동 렌더링](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 이중 버퍼링 된 그래픽을 렌더링 하는 방법을 보여 줍니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 이중 버퍼링을 사용 하도록 설정 하는 제어 메서드.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 그래픽 버퍼를 만드는 방법을 제공 합니다.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 버퍼링 된 그래픽 컨텍스트에 응용 프로그램 도메인에 대 한 액세스를 제공합니다.
