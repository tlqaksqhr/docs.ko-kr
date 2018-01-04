---
title: "ImeMode 속성을 사용하여 전자 단어 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5971fd9a75f936d2ec63eea6a086c681ec996652
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a><span data-ttu-id="d1a7c-102">ImeMode 속성을 사용하여 전자 단어 표시</span><span class="sxs-lookup"><span data-stu-id="d1a7c-102">Display of Asian Characters with the ImeMode Property</span></span>
<span data-ttu-id="d1a7c-103"><xref:System.Windows.Forms.Control.ImeMode%2A> 속성 폼과 컨트롤에서 입력된 방법 편집기 (입력기)에 대 한 특정 모드를 강제 적용을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a7c-103">The <xref:System.Windows.Forms.Control.ImeMode%2A> property is used by forms and controls to force a specific mode for an input method editor (IME).</span></span> <span data-ttu-id="d1a7c-104">IME는 일반 키보드로 인코딩할 수 있는 것보다 더 많은 문자를 포함하고 있으므로 중국어, 일본어 및 한국어 스크립트를 작성하는 데 필수적인 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a7c-104">The IME is an essential component for writing Chinese, Japanese, and Korean scripts, since these writing systems have more characters than can be encoded for a regular keyboard.</span></span> <span data-ttu-id="d1a7c-105">예를 들어 특정 텍스트 상자에 ASCII 문자만 허용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a7c-105">For example, you may want to allow only ASCII characters in a particular text box.</span></span> <span data-ttu-id="d1a7c-106">이러한 경우에 설정할 수 있습니다는 <xref:System.Windows.Forms.Control.ImeMode%2A> 속성을 <xref:System.Windows.Forms.ImeMode> 해당 특정 텍스트 상자에 대 한 ASCII 문자를 입력할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a7c-106">In such a case you can set the <xref:System.Windows.Forms.Control.ImeMode%2A> property to <xref:System.Windows.Forms.ImeMode> and users will only be able to enter ASCII characters for that particular text box.</span></span> <span data-ttu-id="d1a7c-107">기본값은 <xref:System.Windows.Forms.Control.ImeMode%2A> 속성은 <xref:System.Windows.Forms.ImeMode>이므로 양식의 모든 컨트롤 폼에 대 한 속성을 설정 하는 경우 해당 설정을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a7c-107">The default value of the <xref:System.Windows.Forms.Control.ImeMode%2A> property is <xref:System.Windows.Forms.ImeMode>, so if you set the property for a form, all controls on the form will inherit that setting.</span></span> <span data-ttu-id="d1a7c-108">자세한 내용은 참조 <xref:System.Windows.Forms.Control.ImeMode%2A> ) 및 <xref:System.Windows.Forms.ImeMode>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a7c-108">For more information, see <xref:System.Windows.Forms.Control.ImeMode%2A> ) and <xref:System.Windows.Forms.ImeMode>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a7c-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1a7c-109">See Also</span></span>  
 [<span data-ttu-id="d1a7c-110">Windows Forms 전역화</span><span class="sxs-lookup"><span data-stu-id="d1a7c-110">Globalizing Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)
