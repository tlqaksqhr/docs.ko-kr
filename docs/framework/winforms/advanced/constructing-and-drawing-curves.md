---
title: "곡선 구성 및 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62e9b9e0e1aa432578b7173cd58f88dd44957f84
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="49c75-102">곡선 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="49c75-102">Constructing and Drawing Curves</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="49c75-103">에서는 여러 유형의 곡선 지원: 타원, 타원, 카디널 스플라인 및 베 지 어 스플라인을 합니다.</span><span class="sxs-lookup"><span data-stu-id="49c75-103"> supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="49c75-104">타원의 경계 사각형;에 의해 정의 됩니다. 호는 시작 각도 및 스윕 각도에서 정의 되는 타원의 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="49c75-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="49c75-105">카디널 스플라인 포인트와 장력 매개 변수 배열에 의해 정의 된-곡선 배열의 각 요소를 원활 하 게 전달 하 고 장력 매개 변수 곡률 하는 방식에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="49c75-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="49c75-106">두 개의 끝점과 곡선의 제어점 통과 하지 않으므로 두 개의 제어점 되는 베 지 어 스플라인을 정의 되어 있지만 제어점 방향 및 곡선을 다른 한 쪽 끝점에서 면 구부러지지.</span><span class="sxs-lookup"><span data-stu-id="49c75-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49c75-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="49c75-107">In This Section</span></span>  
 [<span data-ttu-id="49c75-108">방법: 카디널 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="49c75-108">How to: Draw Cardinal Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="49c75-109">카디널 스플라인 및을 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="49c75-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="49c75-110">방법: 단일 3차원 곡선 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="49c75-110">How to: Draw a Single Bézier Spline</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="49c75-111">베 지 어 스플라인 및 그리는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="49c75-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="49c75-112">방법: 일련의 3차원 곡선 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="49c75-112">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="49c75-113">시퀀스에서 여러 베 지 어 스플라인을 그립니다 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="49c75-113">Explains how to draw several Bézier splines in sequence.</span></span>
