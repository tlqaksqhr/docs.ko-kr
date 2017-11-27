---
title: "Graphics 컨테이너 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 337057e10e03712aa93b00d9c687374e53f8dd03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="using-graphics-containers"></a><span data-ttu-id="c15b0-102">Graphics 컨테이너 사용</span><span class="sxs-lookup"><span data-stu-id="c15b0-102">Using Graphics Containers</span></span>
<span data-ttu-id="c15b0-103">A <xref:System.Drawing.Graphics> 개체와 같은 메서드를 제공 <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, 및 <xref:System.Drawing.Graphics.DrawString%2A> 벡터 이미지, 래스터 이미지 및 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15b0-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="c15b0-104">A <xref:System.Drawing.Graphics> 개체에 나타나는 항목의 방향과 품질에 영향을 주는 몇 가지 속성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15b0-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="c15b0-105">예를 들어 다듬기 모드 속성은 여부 선 및 곡선 앤티 앨리어싱 적용 되 고 위치 및 회전에 나타나는 항목의 전역 변환 속성에 영향을 줍니다 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15b0-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="c15b0-106">A <xref:System.Drawing.Graphics> 개체는 특정 디스플레이 장치에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15b0-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="c15b0-107">사용 하는 경우는 <xref:System.Drawing.Graphics> 창에 그릴 개체는 <xref:System.Drawing.Graphics> 또한 개체는 해당 특정 창에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15b0-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="c15b0-108">A <xref:System.Drawing.Graphics> 개체 간주할 수의 컨테이너 드로잉 영향을 미치는 속성 집합을 포함 하기 때문에 있으며 장치 관련 정보에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15b0-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="c15b0-109">기존 내에서 보조 컨테이너를 만들 수 <xref:System.Drawing.Graphics> 호출 하 여 개체는 <xref:System.Drawing.Graphics.BeginContainer%2A> 하는 방식의 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c15b0-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c15b0-110">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c15b0-110">In This Section</span></span>  
 [<span data-ttu-id="c15b0-111">Graphics 개체의 상태 관리</span><span class="sxs-lookup"><span data-stu-id="c15b0-111">Managing the State of a Graphics Object</span></span>](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="c15b0-112">설명 어떻게 품질 설정, 클리핑 영역 및 변환의 관리는 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c15b0-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="c15b0-113">중첩된 Graphics 컨테이너 사용</span><span class="sxs-lookup"><span data-stu-id="c15b0-113">Using Nested Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 <span data-ttu-id="c15b0-114">컨테이너의 상태를 제어를 사용 하는 방법을 보여 줍니다는 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c15b0-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
