---
title: Authorizing Access to Service Operations
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: b7f8b9b5fc4e6524da49b4d3f23de90a123e92e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33501483"
---
# <a name="authorizing-access-to-service-operations"></a><span data-ttu-id="afdf4-102">Authorizing Access to Service Operations</span><span class="sxs-lookup"><span data-stu-id="afdf4-102">Authorizing Access to Service Operations</span></span>
<span data-ttu-id="afdf4-103">이 샘플에 사용 하는 방법을 보여 줍니다는 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) 사용할 수 있도록는 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 특성을 서비스 작업에 대 한 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-103">This sample demonstrates how to use the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span> <span data-ttu-id="afdf4-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="afdf4-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) sample.</span></span> <span data-ttu-id="afdf4-105">서비스와 클라이언트를 사용 하 여 구성 된는 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-105">The service and client are configured using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="afdf4-106">`mode` 특성에는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 가로 설정 된 `Message` 및 `clientCredentialType` 가로 설정 된 `Windows`합니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-106">The `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="afdf4-107"><xref:System.Security.Permissions.PrincipalPermissionAttribute>는 각 서비스 메서드에 적용되고 각 작업에 대한 액세스를 제한하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-107">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each service method and used to restrict access to each operation.</span></span> <span data-ttu-id="afdf4-108">호출자는 각 작업에 액세스하기 위해 Windows 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-108">The caller must be a Windows administrator to access each operation.</span></span>  
  
 <span data-ttu-id="afdf4-109">이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-109">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afdf4-110">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="afdf4-111">서비스 구성 파일에서는 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) 설정 하 여 `principalPermissionMode` 특성:</span><span class="sxs-lookup"><span data-stu-id="afdf4-111">The service configuration file uses the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to set the `principalPermissionMode` attribute:</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>   
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="afdf4-112">`principalPermissionMode`를 `UseWindowsGroups`로 설정하면 Windows 그룹 이름에 기초하여 <xref:System.Security.Permissions.PrincipalPermissionAttribute>를 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-112">Setting the `principalPermissionMode` to `UseWindowsGroups` enables the use of <xref:System.Security.Permissions.PrincipalPermissionAttribute> based on Windows group names.</span></span>  
  
 <span data-ttu-id="afdf4-113">다음 샘플 코드와 같이 <xref:System.Security.Permissions.PrincipalPermissionAttribute>가 각 작업에 적용되어 호출자가 Windows 관리자 그룹의 일부여야 한다는 것을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-113">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each operation to require the caller to be part of the Windows administrators group, as shown in the following sample code.</span></span>  
  
```  
[PrincipalPermission(SecurityAction.Demand,   
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 <span data-ttu-id="afdf4-114">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-114">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="afdf4-115">클라이언트는 관리자 그룹의 일부인 계정으로 실행 중인 경우 각 작업과 통신할 수 있고, 그렇지 않은 경우 액세스가 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-115">The client successfully communicates with each operation if it is running under an account that is part of the Administrators group; otherwise, access is denied.</span></span> <span data-ttu-id="afdf4-116">권한 부여 오류를 테스트하려면 관리자 그룹의 일부가 아닌 계정으로 클라이언트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-116">To experiment with authorization failure, run the client under an account that is not part of the Administrators group.</span></span> <span data-ttu-id="afdf4-117">클라이언트를 종료하려면 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-117">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="afdf4-118"><xref:System.ServiceModel.Dispatcher.IErrorHandler>를 구현하여 권한 부여 오류를 서비스에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-118">A service can be notified of authorization failures by implementing an <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span></span> <span data-ttu-id="afdf4-119">참조 [확장 제어를 통해 오류를 처리 하 고 보고](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) 구현에 대 한 내용은 `IErrorHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-119">See [Extending Control Over Error Handling and Reporting](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) for information about implementing `IErrorHandler`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="afdf4-120">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="afdf4-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="afdf4-121">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="afdf4-122">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="afdf4-123">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afdf4-123">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afdf4-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afdf4-124">See Also</span></span>
