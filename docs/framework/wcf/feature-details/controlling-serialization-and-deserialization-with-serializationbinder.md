---
title: "SerializationBinder를 사용하여 serialization 및 deserialization 제어"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be5faf5e465eeacc190081c22d7bc59c3caf5825
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a><span data-ttu-id="71336-102">SerializationBinder를 사용하여 serialization 및 deserialization 제어</span><span class="sxs-lookup"><span data-stu-id="71336-102">Controlling Serialization and Deserialization with SerializationBinder</span></span>
<span data-ttu-id="71336-103">serialization 도중에, 포맷터는 올바른 형식 및 버전의 개체 인스턴스를 만드는 데 필요한 정보를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="71336-103">During serialization, a formatter transmits the information required to create an instance of an object of the correct type and version.</span></span> <span data-ttu-id="71336-104">이 정보에는 일반적으로 개체에 대한 어셈블리 이름 및 전체 형식 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="71336-104">This information generally includes the full type name and assembly name of the object.</span></span> <span data-ttu-id="71336-105">기본적으로 deserialization은 이 정보를 사용하여 동일한 개체의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="71336-105">By default, deserialization uses this information to create an instance of an identical object.</span></span> <span data-ttu-id="71336-106">deserialization을 수행하는 컴퓨터에 원본 클래스가 없거나, 원본 클래스가 어셈블리 간에 이동했거나, 서버와 클라이언트에 서로 다른 버전의 클래스가 필요한 경우 일부 사용자는 serialize 및 deserialize할 클래스를 제어해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71336-106">Some users may need to control which class to serialize and deserialize, either because the original class may not exist on the machine performing deserialization, the original class has moved between assemblies, or a different version of the class is required on the server and client.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="71336-107">[Serialization 바인더 사용](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71336-107"> [Usage of Serialization Binder](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="71336-108">이 기능은 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 또는 <xref:System.Runtime.Serialization.NetDataContractSerializer>를 사용할 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71336-108">This functionality is only available when using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or the <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span>  
  
## <a name="using-serializationbinder"></a><span data-ttu-id="71336-109">SerializationBinder 사용</span><span class="sxs-lookup"><span data-stu-id="71336-109">Using SerializationBinder</span></span>  
 <span data-ttu-id="71336-110"><xref:System.Runtime.Serialization.SerializationBinder>는 serialization 및 deserialization 중에 사용되는 실제 형식을 제어하는 데 사용되는 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="71336-110"><xref:System.Runtime.Serialization.SerializationBinder> is an abstract class used to control the actual types used during serialization and deserialization.</span></span> <span data-ttu-id="71336-111">serialization 및 deserialization 중에 사용되는 형식을 제어하려면 <xref:System.Runtime.Serialization.SerializationBinder>에서 클래스를 파생시키고 <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> 및 <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="71336-111">To control the types used during serialization and deserialization, derive a class from <xref:System.Runtime.Serialization.SerializationBinder> and override the <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> and <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> methods.</span></span> <span data-ttu-id="71336-112"><xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> 메서드는 <xref:System.Type>을 받아서 어셈블리 및 형식 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="71336-112">The <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> method takes a <xref:System.Type> and returns an assembly and type name.</span></span> <span data-ttu-id="71336-113"><xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> 메서드는 어셈블리 및 형식 이름을 받아서 <xref:System.Type>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="71336-113">The <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> method takes an assembly and type name and returns a <xref:System.Type>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71336-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71336-114">See Also</span></span>  
 [<span data-ttu-id="71336-115">Serialization 및 Deserialization</span><span class="sxs-lookup"><span data-stu-id="71336-115">Serialization and Deserialization</span></span>](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [<span data-ttu-id="71336-116">Serialization 바인더 사용</span><span class="sxs-lookup"><span data-stu-id="71336-116">Usage of Serialization Binder</span></span>](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)
