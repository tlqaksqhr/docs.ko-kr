---
title: "ErrorProvider 구성 요소 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 589735156ad4d6d639c2449d6bd693e2b3a32d50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="errorprovider-component-overview-windows-forms"></a><span data-ttu-id="e0fc8-102">ErrorProvider 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e0fc8-102">ErrorProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="e0fc8-103">Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) 구성 요소는 폼 또는 컨트롤에서 사용자 입력의 유효성을 검사 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-103">The Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) component is used to validate user input on a form or control.</span></span> <span data-ttu-id="e0fc8-104">일반적으로 폼에서 사용자 입력 유효성 검사 또는 데이터 집합의 오류 표시와 함께에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-104">It is typically used in conjunction with validating user input on a form, or displaying errors within a dataset.</span></span> <span data-ttu-id="e0fc8-105">오류 공급자 방법이 더 나은 오류 메시지를 메시지 상자에 표시 이므로 메시지 상자가 해제 되 면 오류 메시지가 더 이상 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-105">An error provider is a better alternative than displaying an error message in a message box, because once a message box is dismissed, the error message is no longer visible.</span></span> <span data-ttu-id="e0fc8-106"><xref:System.Windows.Forms.ErrorProvider> 오류 아이콘을 표시 하는 구성 요소 (![ErrorProvider 아이콘](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) 텍스트 상자; 위에 마우스 포인터를 놓을 때와 같이 관련 컨트롤 옆에 도구 설명이 나타납니다 오류 아이콘, 오류 메시지 문자열을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-106">The <xref:System.Windows.Forms.ErrorProvider> component displays an error icon (![ErrorProvider icon](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) next to the relevant control, such as a text box; when the user positions the mouse pointer over the error icon, a ToolTip appears, showing the error message string.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="e0fc8-107">키 속성</span><span class="sxs-lookup"><span data-stu-id="e0fc8-107">Key Properties</span></span>  
 <span data-ttu-id="e0fc8-108"><xref:System.Windows.Forms.ErrorProvider> 구성 요소의 주요 속성은 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, 및 <xref:System.Windows.Forms.ErrorProvider.Icon%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-108">The <xref:System.Windows.Forms.ErrorProvider> component's key properties are <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, and <xref:System.Windows.Forms.ErrorProvider.Icon%2A>.</span></span> <span data-ttu-id="e0fc8-109">사용 하는 경우 <xref:System.Windows.Forms.ErrorProvider> 구성 요소 데이터 바인딩된 컨트롤에는 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 속성 폼에 오류 아이콘이 표시 하려면 구성 요소에서 적절 한 컨테이너 (일반적으로 Windows Form)으로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-109">When using <xref:System.Windows.Forms.ErrorProvider> component with data-bound controls, the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property must be set to the appropriate container (usually the Windows Form) in order for the component to display an error icon on the form.</span></span> <span data-ttu-id="e0fc8-110">구성 요소 디자이너에 추가 되는 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 포함 하는 폼 속성이; 코드에서 컨트롤을 추가 하면 직접 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-110">When the component is added in the designer, the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property is set to the containing form; if you add the control in code, you must set it yourself.</span></span>  
  
 <span data-ttu-id="e0fc8-111"><xref:System.Windows.Forms.ErrorProvider.Icon%2A> 기본값 대신 사용자 지정 오류 아이콘으로 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-111">The <xref:System.Windows.Forms.ErrorProvider.Icon%2A> property can be set to a custom error icon instead of the default.</span></span> <span data-ttu-id="e0fc8-112">경우는 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> 속성이 설정 되어는 <xref:System.Windows.Forms.ErrorProvider> 구성 요소는 데이터 집합에 대 한 오류 메시지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-112">When the <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> property is set, the <xref:System.Windows.Forms.ErrorProvider> component can display error messages for a dataset.</span></span> <span data-ttu-id="e0fc8-113">주요 메서드는 <xref:System.Windows.Forms.ErrorProvider> 구성 요소는는 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드에서 오류 메시지 문자열을 지정 하는 오류 아이콘이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-113">The key method of the <xref:System.Windows.Forms.ErrorProvider> component is the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method, which specifies the error message string and where the error icon should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0fc8-114"><xref:System.Windows.Forms.ErrorProvider> 구성 요소 액세스 가능 클라이언트에 대 한 기본 제공 지원을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-114">The <xref:System.Windows.Forms.ErrorProvider> component does not provide built-in support for accessibility clients.</span></span> <span data-ttu-id="e0fc8-115">응용 프로그램에 액세스할 수 있도록이 구성 요소를 사용 하는 경우, 추가, 액세스할 수 있는 피드백 메커니즘을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fc8-115">To make your application accessible when using this component, you must provide an additional, accessible feedback mechanism.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0fc8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0fc8-116">See Also</span></span>  
 <xref:System.Windows.Forms.ErrorProvider>  
 [<span data-ttu-id="e0fc8-117">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 집합에 있는 오류 보기</span><span class="sxs-lookup"><span data-stu-id="e0fc8-117">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)  
 [<span data-ttu-id="e0fc8-118">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="e0fc8-118">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
