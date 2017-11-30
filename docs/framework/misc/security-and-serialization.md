---
title: "보안 및 Serialization"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, serialization
- serialization, security
- secure coding, serialization
- security [.NET Framework], serialization
ms.assetid: b921bc94-bd3a-4c91-9ede-2c8d4f78ea9a
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9897bbfff542bf708f8fbbc1ac29f7688a1590ac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="security-and-serialization"></a><span data-ttu-id="22948-102">보안 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="22948-102">Security and Serialization</span></span>
<span data-ttu-id="22948-103">다른 방법으로는 액세스할 수 없는 개체 인스턴스 데이터를 직렬화를 통해 다른 코드에서 보거나 수정할 수 있으므로 <xref:System.Security.Permissions.SecurityPermission> 플래그가 지정된 <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> 의 직렬화를 수행하려면 코드에 특수 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="22948-103">Because serialization can allow other code to see or modify object instance data that would otherwise be inaccessible, a special permission is required of code performing serialization: <xref:System.Security.Permissions.SecurityPermission> with the <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> flag specified.</span></span> <span data-ttu-id="22948-104">기본 정책에 따라 이 권한은 인터넷에서 다운로드한 코드나 인트라넷 코드에는 부여되지 않고 로컬 컴퓨터에 있는 코드에만 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="22948-104">Under default policy, this permission is not given to Internet-downloaded or intranet code; only code on the local computer is granted this permission.</span></span>  
  
 <span data-ttu-id="22948-105">일반적으로 개체 인스턴스의 모든 필드가 직렬화되며 이는 해당 데이터가 인스턴스에 대해 직렬화된 데이터로 표시됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="22948-105">Normally, all fields of an object instance are serialized, meaning that data is represented in the serialized data for the instance.</span></span> <span data-ttu-id="22948-106">멤버의 접근성과 관계 없이, 코드가 형식을 해석하여 데이터 값을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22948-106">It is possible for code that can interpret the format to determine what the data values are, independent of the accessibility of the member.</span></span> <span data-ttu-id="22948-107">마찬가지로, 접근성 규칙과 관계 없이 역직렬화를 통해 직렬화된 표현에서 데이터를 추출하고 개체 상태를 직접 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22948-107">Similarly, deserialization extracts data from the serialized representation and sets object state directly, again irrespective of accessibility rules.</span></span>  
  
 <span data-ttu-id="22948-108">보안에 민감한 데이터를 포함할 수 있는 모든 개체는 가능하면 직렬화할 수 없도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22948-108">Any object that could contain security-sensitive data should be made nonserializable, if possible.</span></span> <span data-ttu-id="22948-109">이러한 개체를 직렬화할 수 있도록 설정해야 하는 경우에는, 민감한 데이터가 포함된 특정 필드를 직렬화할 수 없도록 설정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="22948-109">If it must be serializable, try to make specific fields that hold sensitive data nonserializable.</span></span> <span data-ttu-id="22948-110">이렇게 할 수 없는 경우, 직렬화할 수 있는 권한이 있는 모든 코드에 민감한 데이터가 노출되므로 악성 코드가 이러한 권한을 갖지 않도록 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22948-110">If this cannot be done, be aware that this data will be exposed to any code that has permission to serialize, and make sure that no malicious code can get this permission.</span></span>  
  
 <span data-ttu-id="22948-111"><xref:System.Runtime.Serialization.ISerializable> 인터페이스는 직렬화 인프라에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="22948-111">The <xref:System.Runtime.Serialization.ISerializable> interface is intended for use only by the serialization infrastructure.</span></span> <span data-ttu-id="22948-112">하지만 보호되지 않는 경우에는 중요 중보가 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22948-112">However, if unprotected, it can potentially release sensitive information.</span></span> <span data-ttu-id="22948-113">**ISerializable**을 구현하여 사용자 지정 직렬화를 제공할 때는 다음 예방 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22948-113">If you provide custom serialization by implementing **ISerializable**, make sure you take the following precautions:</span></span>  
  
-   <span data-ttu-id="22948-114"><xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> SerializationFormatter **권한을 지정하여** SecurityPermission **을 요청하거나 메서드 출력에 중요 정보가 노출되지 않도록 하여** 메서드의 보안을 명시적으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22948-114">The <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> method should be explicitly secured either by demanding the **SecurityPermission** with **SerializationFormatter** permission specified or by making sure that no sensitive information is released with the method output.</span></span> <span data-ttu-id="22948-115">예:</span><span class="sxs-lookup"><span data-stu-id="22948-115">For example:</span></span>  
  
    ```vb  
    Public Overrides<SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)>  _  
    Sub GetObjectData(info As SerializationInfo, context As StreamingContext)  
    End Sub  
    ```  
  
    ```csharp  
    [SecurityPermissionAttribute(SecurityAction.Demand,SerializationFormatter   
    =true)]  
    public override void GetObjectData(SerializationInfo info,   
    StreamingContext context)  
    {  
    }  
    ```  
  
-   <span data-ttu-id="22948-116">직렬화에 사용되는 특수 생성자는 엄격한 입력 유효성 검사를 수행해야 하며 악성 코드가 악용할 수 없도록 보호하거나 비공개로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22948-116">The special constructor used for serialization should also perform thorough input validation and should be either protected or private to help protect against misuse by malicious code.</span></span> <span data-ttu-id="22948-117">클래스를 명시적으로 만들거나 일종의 팩터리를 통해 간접적으로 만드는 경우와 같이 기타 모든 방법으로 이러한 클래스의 인스턴스를 가져오려면 이와 같은 보안 검사 및 권한을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22948-117">It should enforce the same security checks and permissions required to obtain an instance of such a class by any other means, such as explicitly creating the class or indirectly creating it through some kind of factory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22948-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22948-118">See Also</span></span>  
 [<span data-ttu-id="22948-119">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="22948-119">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
