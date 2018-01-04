---
title: "FontDialog 구성 요소 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9e3018d024254adb249860f7736399e7f2da72a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="39348-102">FontDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="39348-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="39348-103">Windows Forms <xref:System.Windows.Forms.FontDialog> 구성 요소는 표준 windows는 미리 구성 된 대화 상자, **글꼴** 시스템에 현재 설치 되어 있는 글꼴을 노출 하는 데 사용 되는 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="39348-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="39348-104">글꼴 선택 대화 상자를 직접 구성 하는 대신에 대 한 간단한 솔루션으로 Windows 기반 응용 프로그램 내에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="39348-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="39348-105">기본적으로 대화 상자 글꼴에 대 한 목록 상자에 표시 된 글꼴 스타일 및 Size; 취소선, 밑줄; 등의 효과 대 한 확인란 스크립트;에 대 한 드롭다운 목록 및 글꼴을 어떻게 나타나는지 샘플을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="39348-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="39348-106">(스크립트 참조 지정된 된 글꼴에 사용할 수 있는 다양 한 문자 스크립트 예를 들어, 히브리어 또는 일본어.) 글꼴 대화 상자를 표시 하려면 호출 된 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="39348-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="39348-107">키 속성</span><span class="sxs-lookup"><span data-stu-id="39348-107">Key Properties</span></span>  
 <span data-ttu-id="39348-108">구성 요소에 다양 한 모양을 구성 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="39348-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="39348-109">대화 상자 선택 항목을 설정 하는 속성은 <xref:System.Windows.Forms.FontDialog.Font%2A> 및 <xref:System.Windows.Forms.FontDialog.Color%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="39348-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="39348-110"><xref:System.Windows.Forms.FontDialog.Font%2A> 글꼴, 스타일, 크기, 스크립트 및 효과; 속성 설정 예를 들어 `Arial, 10pt, style=Italic, Strikeout`합니다.</span><span class="sxs-lookup"><span data-stu-id="39348-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39348-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39348-111">See Also</span></span>  
 <xref:System.Windows.Forms.FontDialog>  
 [<span data-ttu-id="39348-112">FontDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="39348-112">FontDialog Component</span></span>](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
