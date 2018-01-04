---
title: "그래픽 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3438fe2f1c3a6fc40efda0ff2583208f38bf7d5c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="overview-of-graphics"></a>그래픽 개요
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]응용 프로그래밍 인터페이스 (API)는 Microsoft Windows 운영 체제의 하위 시스템을 구성 하는입니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]화면과 프린터에 정보를 표시 하는 일을 담당 합니다. 이름에서 알 수 있듯이, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 이전 버전의 Windows에 포함된 그래픽 장치 인터페이스인 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]의 후속 프로그램입니다.  
  
## <a name="managed-class-interface"></a>관리되는 클래스 인터페이스  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API 관리 코드로 배포 된 클래스 집합을 통해 노출 됩니다. 이 클래스 집합을 라고는 *관리 되는 클래스 인터페이스* 를 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]합니다. 다음 네임스페이스는 관리되는 클래스 인터페이스를 구성합니다.  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 그래픽 장치 인터페이스와 같은 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 특정 디스플레이 장치의 세부 정보를 염려 하지 않고 화면 또는 프린터에 정보를 표시할 수 있습니다. 프로그래머가 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 클래스에서 제공하는 메서드를 호출합니다. 이러한 메서드가 다시 특정 장치 드라이버에 대한 적절한 호출을 수행합니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 그래픽 하드웨어에서 응용 프로그램을 분리합니다. 이기이는 프로그래머가 장치 독립적인 응용 프로그램을 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [그래픽 개요](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)
