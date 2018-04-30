---
title: 워크플로 서비스에서 Serialization 구성
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47c66077da051fd70300e1961593e906fe8e77aa
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="b1b40-102">워크플로 서비스에서 Serialization 구성</span><span class="sxs-lookup"><span data-stu-id="b1b40-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="b1b40-103">워크플로 서비스는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스이기 때문에 <xref:System.Runtime.Serialization.DataContractSerializer>(기본값) 또는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-103">Workflow services are [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="b1b40-104">워크플로가 아닌 서비스를 작성할 때 사용할 직렬화기 형식은 서비스 또는 작업 계약에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="b1b40-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 워크플로 서비스를 만드는 경우에는 이러한 계약이 코드로 지정되지 않고 런타임에 계약 유추를 통해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-105">When creating [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="b1b40-106">계약 유추에 대 한 자세한 내용은 참조 [워크플로에서 계약 사용 하 여](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="b1b40-107">직렬화기는 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> 속성을 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="b1b40-108">다음 그림과 같이 디자이너에서 이 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="b1b40-109">![Serializer 설정](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span><span class="sxs-lookup"><span data-stu-id="b1b40-109">![Setting the serializer](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span></span>  
  
 <span data-ttu-id="b1b40-110">다음 예제와 같이 코드에서 직렬화기를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
```  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
 <span data-ttu-id="b1b40-111">워크플로 서비스에서 알려진 형식도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="b1b40-112">알려진 형식에 대 한 자세한 내용은 참조 [데이터 계약 알려진 형식을](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-112">For more information about Known Types see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="b1b40-113">디자이너나 코드에서 알려진 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="b1b40-114">디자이너에서 알려진 형식을 지정하려면 다음 그림과 같이 <xref:System.ServiceModel.Activities.Receive> 작업에 대한 속성 창에서 KnownTypes 속성 옆에 있는 줄임표 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the properties window for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="b1b40-115">![KnownTypes 속성](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span><span class="sxs-lookup"><span data-stu-id="b1b40-115">![KnownTypes property](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span></span>  
  
 <span data-ttu-id="b1b40-116">알려진 형식을 검색하고 지정할 수 있는 형식 컬렉션 편집기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-116">This will display the Type Collections Editor that will allow you to search for and specify known types.</span></span>  
  
 <span data-ttu-id="b1b40-117">![알려진된 형식 추가](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span><span class="sxs-lookup"><span data-stu-id="b1b40-117">![Adding Known Types](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span></span>  
  
 <span data-ttu-id="b1b40-118">클릭는 **새 유형을 추가** 에 연결 하 고 알려진된 형식 컬렉션에 추가 하도록 선택 하거나 검색 유형에 대 한 드롭다운을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="b1b40-119">코드에서 알려진 형식을 지정하려면 다음 예제와 같이 <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
```  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
            approveExpense.KnownTypes.Add(typeof(Travel));  
            approveExpense.KnownTypes.Add(typeof(Meal));  
```  
  
 <span data-ttu-id="b1b40-120">구성 요소를 참조는 워크플로 서비스에 대 한 직렬화를 구성 하는 방법을 보여 주는 전체 코드 예제를 보려면 [워크플로 서비스에서 메시지 서식 지정](../../../../docs/framework/windows-workflow-foundation/samples/formatting-messages-in-workflow-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b40-120">To see a complete code example showing how to configure serialization for a workflow service see [Formatting messages in Workflow Services](../../../../docs/framework/windows-workflow-foundation/samples/formatting-messages-in-workflow-services.md).</span></span>
