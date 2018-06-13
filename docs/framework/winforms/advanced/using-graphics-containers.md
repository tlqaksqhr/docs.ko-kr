---
title: Graphics 컨테이너 사용
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: 8755a95434d3fed06a55cfca0f71d86e5521cb39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525023"
---
# <a name="using-graphics-containers"></a>Graphics 컨테이너 사용
A <xref:System.Drawing.Graphics> 개체와 같은 메서드를 제공 <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, 및 <xref:System.Drawing.Graphics.DrawString%2A> 벡터 이미지, 래스터 이미지 및 텍스트를 표시 합니다. A <xref:System.Drawing.Graphics> 개체에 나타나는 항목의 방향과 품질에 영향을 주는 몇 가지 속성에 있습니다. 예를 들어 다듬기 모드 속성은 여부 선 및 곡선 앤티 앨리어싱 적용 되 고 위치 및 회전에 나타나는 항목의 전역 변환 속성에 영향을 줍니다 결정 합니다.  
  
 A <xref:System.Drawing.Graphics> 개체는 특정 디스플레이 장치에 연결 합니다. 사용 하는 경우는 <xref:System.Drawing.Graphics> 창에 그릴 개체는 <xref:System.Drawing.Graphics> 또한 개체는 해당 특정 창에 연결 합니다.  
  
 A <xref:System.Drawing.Graphics> 개체 간주할 수의 컨테이너 드로잉 영향을 미치는 속성 집합을 포함 하기 때문에 있으며 장치 관련 정보에 연결 됩니다. 기존 내에서 보조 컨테이너를 만들 수 <xref:System.Drawing.Graphics> 호출 하 여 개체는 <xref:System.Drawing.Graphics.BeginContainer%2A> 하는 방식의 <xref:System.Drawing.Graphics> 개체입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [Graphics 개체의 상태 관리](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 설명 어떻게 품질 설정, 클리핑 영역 및 변환의 관리는 <xref:System.Drawing.Graphics> 개체입니다.  
  
 [중첩된 Graphics 컨테이너 사용](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 컨테이너의 상태를 제어를 사용 하는 방법을 보여 줍니다는 <xref:System.Drawing.Graphics> 개체입니다.
