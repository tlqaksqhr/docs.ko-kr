---
title: "사용자 지정 활동 디자이너 및 템플릿 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1aab82e7-7f89-4255-be46-526b09ceeb8b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9064f56dab2c7a2b36394f6f77ded77edc0b387b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="using-custom-activity-designers-and-templates"></a><span data-ttu-id="1bfa1-102">사용자 지정 활동 디자이너 및 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="1bfa1-102">Using Custom Activity Designers and Templates</span></span>
<span data-ttu-id="1bfa1-103">이 단원의 항목에서는 사용자 지정 활동 디자이너와 사용자 지정 활동 템플릿을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1bfa1-103">This section contains topics describing how to create custom activity designers and custom activity templates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1bfa1-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="1bfa1-104">In This Section</span></span>  
 [<span data-ttu-id="1bfa1-105">방법: 사용자 지정 활동 디자이너 만들기</span><span class="sxs-lookup"><span data-stu-id="1bfa1-105">How to: Create a Custom Activity Designer</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer.md)  
 <span data-ttu-id="1bfa1-106">워크플로에서 제공된 디자이너가 디자인 작업에 적합하지 않을 경우 사용자 지정 활동 디자이너를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1bfa1-106">Describes how create a customized activity designer when the designers provided by the workflow are not appropriate to the design tasks.</span></span>  
  
 [<span data-ttu-id="1bfa1-107">방법: 사용자 지정 활동 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="1bfa1-107">How to: Create a Custom Activity Template</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-activity-template.md)  
 <span data-ttu-id="1bfa1-108">사용자가 각 활동을 개별적으로 만들고 해당 속성과 기타 설정을 수동으로 구성하지 않아도 되도록 사용자 지정 활동 템플릿을 사용하여 활동을 미리 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1bfa1-108">Describes how to use custom activity templates to preconfigure activities so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span>  
  
 [<span data-ttu-id="1bfa1-109">ModelItem 편집 컨텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="1bfa1-109">Using the ModelItem Editing Context</span></span>](../../../docs/framework/windows-workflow-foundation/using-the-modelitem-editing-context.md)  
 <span data-ttu-id="1bfa1-110">ModelItem 편집 컨텍스트의 기능을 사용하여 디자이너가 호스트와 상호 작용할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1bfa1-110">Describes how to use the features of the ModelItem editing context to allow the designer to interact with the host.</span></span>  
  
 [<span data-ttu-id="1bfa1-111">사용자 지정 작업 속성을 디자이너 컨트롤에 바인딩</span><span class="sxs-lookup"><span data-stu-id="1bfa1-111">Binding a custom activity property to a designer control</span></span>](../../../docs/framework/windows-workflow-foundation/binding-a-custom-activity-property-to-a-designer-control.md)  
 <span data-ttu-id="1bfa1-112">디자이너에서 ListView 컨트롤을 활동 속성에 바인딩하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1bfa1-112">Describes how to bind a listview control to an activity property in the designer.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1bfa1-113">참조</span><span class="sxs-lookup"><span data-stu-id="1bfa1-113">Reference</span></span>  
 <xref:System.Activities.Presentation.ActivityDesigner>  
  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>  
  
 <xref:System.Activities.ActivityAction>  
  
 <xref:System.Activities.Presentation.IActivityTemplateFactory>  
  
 <xref:System.Activities.Presentation.Model.ModelTreeManager>  
  
## <a name="related-sections"></a><span data-ttu-id="1bfa1-114">관련 단원</span><span class="sxs-lookup"><span data-stu-id="1bfa1-114">Related Sections</span></span>  
 [<span data-ttu-id="1bfa1-115">워크플로 디자이너 재호스트</span><span class="sxs-lookup"><span data-stu-id="1bfa1-115">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
  
## <a name="external-resources"></a><span data-ttu-id="1bfa1-116">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="1bfa1-116">External Resources</span></span>  
 [<span data-ttu-id="1bfa1-117">사용자 지정 활동</span><span class="sxs-lookup"><span data-stu-id="1bfa1-117">Custom Activities</span></span>](../../../docs/framework/windows-workflow-foundation/samples/custom-activities.md)
