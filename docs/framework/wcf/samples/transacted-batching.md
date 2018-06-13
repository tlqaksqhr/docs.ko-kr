---
title: 트랜잭션된 일괄 처리
ms.date: 03/30/2017
ms.assetid: ecd328ed-332e-479c-a894-489609bcddd2
ms.openlocfilehash: 7df65b8f3f149deac841010e392f3919b24506b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33508880"
---
# <a name="transacted-batching"></a><span data-ttu-id="538fa-102">트랜잭션된 일괄 처리</span><span class="sxs-lookup"><span data-stu-id="538fa-102">Transacted Batching</span></span>
<span data-ttu-id="538fa-103">이 샘플에서는 MSMQ(메시지 큐)를 사용하여 트랜잭션된 읽기를 일괄 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-103">This sample demonstrates how to batch transacted reads by using Message Queuing (MSMQ).</span></span> <span data-ttu-id="538fa-104">트랜잭션된 일괄 처리는 대기 중인 통신에서 트랜잭션된 읽기의 성능을 최적화하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-104">Transacted Batching is a performance optimization feature for transacted reads in queued communication.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="538fa-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="538fa-106">대기 중인 통신에서 클라이언트는 큐를 사용하여 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-106">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="538fa-107">좀더 정확하게 말하면 클라이언트는 큐에 메시지를 보내고,</span><span class="sxs-lookup"><span data-stu-id="538fa-107">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="538fa-108">서비스는 큐에서 보낸 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-108">The service receives messages from the queue.</span></span> <span data-ttu-id="538fa-109">따라서 서비스와 클라이언트가 동시에 실행되고 있지 않더라도 큐를 사용하여 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-109">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="538fa-110">이 샘플에서는 트랜잭션된 일괄 처리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-110">This sample demonstrates transacted batching.</span></span> <span data-ttu-id="538fa-111">트랜잭션된 일괄 처리는 큐에 있는 많은 메시지를 읽고 처리할 때 단일 트랜잭션을 사용할 수 있도록 하는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-111">Transacted batching is a behavior that enables the use of a single transaction when reading many messages in the queue and processing them.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="538fa-112">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="538fa-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="538fa-113">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-113">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="538fa-114">서비스가 처음 실행되는 경우 서비스에서는 큐가 있는지 확인하고</span><span class="sxs-lookup"><span data-stu-id="538fa-114">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="538fa-115">큐가 없으면 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-115">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="538fa-116">서비스를 처음 실행하여 큐를 만들거나 MSMQ 큐 관리자를 통해 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-116">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="538fa-117">Windows 2008에서 큐를 만들려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="538fa-117">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="538fa-118">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 서버 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-118">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="538fa-119">확장 된 **기능** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-119">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="538fa-120">마우스 오른쪽 단추로 클릭 **개인 메시지 큐**를 선택 하 고 **새로**, **개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-120">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="538fa-121">확인 된 **트랜잭션** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-121">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="538fa-122">입력 `ServiceModelSamplesTransacted` 새 큐의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-122">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="538fa-123">이 샘플에서 클라이언트는 수백 개의 메시지를 배치의 일부로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-123">In this sample the client sends hundreds of messages as part of the batch.</span></span> <span data-ttu-id="538fa-124">일반적으로 서비스 응용 프로그램에서 이러한 작업을 처리하는 데는 어느 정도의 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-124">It is normal for the service application to take some time to process these.</span></span>  
  
3.  <span data-ttu-id="538fa-125">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="538fa-126">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-126">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="538fa-127">작업 그룹에 속해 있거나 Active Directory 통합이 없는 컴퓨터에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="538fa-127">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1.  <span data-ttu-id="538fa-128">기본적으로 <xref:System.ServiceModel.NetMsmqBinding>을 사용하여 전송 보안이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-128">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="538fa-129">MSMQ 전송 보안에 대 한 두 가지 관련 속성은 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> 및 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` 기본적으로 인증 모드 설정 `Windows` 보호 수준으로 설정 되 고 `Sign`합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-129">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="538fa-130">MSMQ에서 인증 및 서명 기능을 제공하려면 도메인에 속해 있어야 하며 MSMQ의 Active Directory 통합 옵션이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-130">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="538fa-131">이 기준에 맞지 않는 컴퓨터에서 이 샘플을 실행하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-131">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
2.  <span data-ttu-id="538fa-132">컴퓨터가 도메인에 속해 있지 않거나 Active Directory 통합이 설치되어 있지 않은 경우에는 다음 샘플 구성과 같이 인증 모드와 보호 수준을 `None`으로 설정하여 전송 보안을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-132">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <behaviors>  
        <serviceBehaviors>  
          <behavior name="ThrottlingBehavior">  
            <serviceMetadata httpGetEnabled="true"/>  
            <serviceThrottling maxConcurrentCalls="5"/>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="BatchingBehavior">  
            <transactedBatching maxBatchSize="100"/>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <services>  
        <service   
            behaviorConfiguration="ThrottlingBehavior"   
            name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                    binding="netMsmqBinding"  
                    bindingConfiguration="Binding1"   
                    behaviorConfiguration="BatchingBehavior"   
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          <endpoint address="mex"  
                    binding="mexHttpBinding"  
                    contract="IMetadataExchange" />  
        </service>  
      </services>  
  
      <bindings>  
        <netMsmqBinding>  
          <binding name="Binding1">  
            <security mode="None" />  
          </binding>  
        </netMsmqBinding>  
      </bindings>  
  
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="538fa-133">샘플을 실행하기 전에 서버와 클라이언트 모두에서 구성을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-133">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="538fa-134">`security``mode`를 `None`으로 설정하는 것은 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> 및 `Message` 보안을 `None`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-134">Setting `security``mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
  
4.  <span data-ttu-id="538fa-135">원격 컴퓨터에서 데이터베이스를 실행하려면 데이터베이스가 상주하는 컴퓨터를 가리키도록 연결 문자열을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-135">To run the database on a remote computer, change the connection string to point to the computer on which the database resides.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="538fa-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="538fa-136">Requirements</span></span>  
 <span data-ttu-id="538fa-137">이 샘플을 실행하려면 MSMQ가 설치되어 있어야 하고 SQL이나 SQL Express가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-137">To run this sample, MSMQ must be installed and SQL or SQL Express is required.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="538fa-138">세부 항목</span><span class="sxs-lookup"><span data-stu-id="538fa-138">Demonstrates</span></span>  
 <span data-ttu-id="538fa-139">이 샘플에서는 트랜잭션된 일괄 처리 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-139">The sample demonstrates transacted batching behavior.</span></span> <span data-ttu-id="538fa-140">트랜잭션된 일괄 처리는 MSMQ의 대기 중인 전송과 함께 제공되는 성능 최적화 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-140">Transacted batching is a performance optimization feature provided with MSMQ queued transport.</span></span>  
  
 <span data-ttu-id="538fa-141">트랜잭션을 사용하여 메시지를 보내고 받는 경우 실제로는 서로 다른 두 개의 트랜잭션이 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-141">When transactions are used to send and receive messages there are actually 2 separate transactions.</span></span> <span data-ttu-id="538fa-142">클라이언트가 트랜잭션의 범위 내에서 메시지를 보낼 때 트랜잭션은 클라이언트 및 클라이언트 큐 관리자의 로컬에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-142">When the client sends messages within the scope of a transaction, the transaction is local to the client and the client queue manager.</span></span> <span data-ttu-id="538fa-143">서비스가 트랜잭션의 범위 내에서 메시지를 받을 때 트랜잭션은 서비스 및 수신 큐 관리자의 로컬에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-143">When the service receives messages within the scope of the transaction, the transaction is local to the service and the receiving queue manager.</span></span> <span data-ttu-id="538fa-144">클라이언트와 서비스가 동일한 트랜잭션에 참여하지 않고 큐에서 보내기 및 받기와 같은 작업을 수행할 때 서로 다른 트랜잭션을 사용한다는 점은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-144">It is very important to remember that the client and the service are not participating in the same transaction; rather they are using different transactions when performing their operations (such as send and receive) with the queue.</span></span>  
  
 <span data-ttu-id="538fa-145">이 샘플에서는 단일 트랜잭션을 사용하여 여러 서비스 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-145">In the sample we use a single transaction for the execution of multiple service operations.</span></span> <span data-ttu-id="538fa-146">이 트랜잭션은 성능 최적화 기능으로만 사용되면 응용 프로그램의 의미 체계에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-146">This is used only as a performance optimization feature and does not impact the semantics of the application.</span></span> <span data-ttu-id="538fa-147">샘플 기반 [트랜잭션 된 MSMQ 바인딩](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-147">The sample is based on [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="538fa-148">설명</span><span class="sxs-lookup"><span data-stu-id="538fa-148">Comments</span></span>  
 <span data-ttu-id="538fa-149">이 샘플에서 클라이언트는 트랜잭션의 범위 내에서 일련의 메시지를 서비스로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-149">In this sample, the client sends a batch of messages to the service from within the scope of a transaction.</span></span> <span data-ttu-id="538fa-150">성능 최적화를 보여 주기 위해 많은 메시지를 보내며, 여기에서는 최대 2,500개의 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-150">To show the performance optimization, we send a large number of messages; in this case, up to 2500 messages.</span></span>  
  
 <span data-ttu-id="538fa-151">그러면 서비스는 큐로 전송된 메시지를 서비스에 정의된 트랜잭션 범위 내에서 받습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-151">The messages sent to the queue are then received by the service within the transaction scope defined by the service.</span></span> <span data-ttu-id="538fa-152">일괄 처리를 수행하지 않으면 각 서비스 작업 호출에 대해 2500개의 트랜잭션이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-152">Without batching, this results in 2500 transactions for each invocation of the service operation.</span></span> <span data-ttu-id="538fa-153">따라서 시스템 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-153">This impacts performance of the system.</span></span> <span data-ttu-id="538fa-154">MSMQ 큐와 `Orders` 데이터베이스라는 두 개의 리소스 관리자가 관련되어 있으므로 각 트랜잭션은 DTC 트랜잭션이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-154">Because two resource managers are involved -the MSMQ queue and the `Orders` database- each such transaction is a DTC transaction.</span></span> <span data-ttu-id="538fa-155">여기에서는 메시지 일괄 처리 및 서비스 작업 호출이 단일 트랜잭션 내에서 수행되도록 하여 훨씬 더 적은 수의 트랜잭션을 사용함으로써 성능을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-155">We optimize this by using a much smaller number of transactions by ensuring that a batch of messages and service operation invocations happen in a single transaction.</span></span>  
  
 <span data-ttu-id="538fa-156">다음과 같이 일괄 처리 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-156">We use the batching feature by:</span></span>  
  
-   <span data-ttu-id="538fa-157">구성에서 트랜잭션된 일괄 처리 동작 지정</span><span class="sxs-lookup"><span data-stu-id="538fa-157">Specifying transacted batching behavior in configuration.</span></span>  
  
-   <span data-ttu-id="538fa-158">단일 트랜잭션을 사용하여 읽을 메시지 수로 일괄 처리 크기 지정</span><span class="sxs-lookup"><span data-stu-id="538fa-158">Specifying a batch size in terms of number of messages to be read using a single transaction.</span></span>  
  
-   <span data-ttu-id="538fa-159">실행할 최대 동시 일괄 처리 수 지정</span><span class="sxs-lookup"><span data-stu-id="538fa-159">Specifying the maximum number of concurrent batches to run.</span></span>  
  
 <span data-ttu-id="538fa-160">이 예제에서는 트랜잭션을 커밋하기 전에 100개의 서비스 작업이 단일 트랜잭션으로 호출되도록 하여 트랜잭션 수를 줄임으로써 성능 향상을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-160">In this example, we show performance gains by reducing the number of transactions by ensuring that 100 service operations are invoked in a single transaction before committing the transaction.</span></span>  
  
 <span data-ttu-id="538fa-161">서비스 동작은 `TransactionScopeRequired`가 `true`로 설정된 작업 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-161">The service behavior defines an operation behavior with `TransactionScopeRequired` set to `true`.</span></span> <span data-ttu-id="538fa-162">따라서 큐에서 메시지를 검색할 때 사용되는 트랜잭션 범위가 메서드에서 액세스하는 리소스 관리자에서 동일하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-162">This ensures that the same transaction scope that is used to retrieve the message from the queue is used by any resource managers accessed by the method.</span></span> <span data-ttu-id="538fa-163">이 예제에서는 기본 데이터베이스를 사용하여 메시지에 포함된 구매 주문 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-163">In this example, we use a basic database to store the purchase order information contained in the message.</span></span> <span data-ttu-id="538fa-164">트랜잭션 범위도 메서드에서 예외가 throw될 경우 큐로 메시지가 반환되도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-164">The transaction scope also guarantees that if the method throws an exception, the message is returned to the queue.</span></span> <span data-ttu-id="538fa-165">이 작업 동작을 설정하지 않으면 대기 중인 채널에서 트랜잭션을 만들어 큐의 메시지를 읽고 디스패치하기 전에 자동으로 커밋하므로 작업이 실패할 경우 메시지가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-165">Without setting this operation behavior, a queued channel creates a transaction to read the message from the queue and commits it automatically before it is dispatched so that if the operation fails, the message is lost.</span></span> <span data-ttu-id="538fa-166">가장 일반적인 시나리오는 다음 코드에 표시된 대로 큐에서 메시지를 읽는 데 사용되는 트랜잭션에 서비스 작업이 참여하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-166">The most common scenario is for service operations to enlist in the transaction that is used to read the message from the queue as demonstrated in the following code.</span></span>  
  
 <span data-ttu-id="538fa-167">`ReleaseServiceInstanceOnTransactionComplete`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-167">Note that `ReleaseServiceInstanceOnTransactionComplete` is set to `false`.</span></span> <span data-ttu-id="538fa-168">이 설정은 일괄 처리에 중요한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-168">This is an important requirement for batching.</span></span> <span data-ttu-id="538fa-169">`ReleaseServiceInstanceOnTransactionComplete`의 `ServiceBehaviorAttribute` 속성은 트랜잭션이 완료된 다음 서비스 인스턴스로 수행할 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-169">The property `ReleaseServiceInstanceOnTransactionComplete` on `ServiceBehaviorAttribute` indicates what to do with the service instance once the transaction is completed.</span></span> <span data-ttu-id="538fa-170">기본적으로 서비스 인스턴스는 트랜잭션이 완료될 때 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-170">By default, the service instance is released upon completing the transaction.</span></span> <span data-ttu-id="538fa-171">일괄 처리에서 중요한 측면은 큐에 있는 많은 메시지를 읽고 디스패치하는 데 단일 트랜잭션을 사용한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-171">The core aspect to batching is the use of a single transaction for reading and dispatching many messages in the queue.</span></span> <span data-ttu-id="538fa-172">따라서 서비스 인스턴스를 해제하면 일괄 처리 사용을 부정하여 영구적인 트랜잭션 완료로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-172">Therefore releasing the service instance ends up completing the transaction prematurely negating the very use of batching.</span></span> <span data-ttu-id="538fa-173">이 속성을 `true`로 설정하고 트랜잭션된 일괄 처리 동작을 끝점에 추가하면 일괄 처리 유효성 검사 동작에서 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-173">If this property is set to `true` and transacted batching behavior is added to the endpoint, the batching validation behavior throws an exception.</span></span>  

```csharp
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(ReleaseServiceInstanceOnTransactionComplete=false,   
TransactionIsolationLevel=  
System.Transactions.IsolationLevel.Serializable, ConcurrencyMode=ConcurrencyMode.Multiple)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                       TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
    …  
}  
```

 <span data-ttu-id="538fa-174">`Orders` 클래스는 주문 처리를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-174">The `Orders` class encapsulates the processing of the order.</span></span> <span data-ttu-id="538fa-175">이 예제에서는 구매 주문 정보로 데이터베이스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-175">In the sample, it updates the database with purchase order information.</span></span>  

```csharp
// Order Processing Logic  
public class Orders  
{  
    public static void Add(PurchaseOrder po)  
    {  
        // Insert purchase order.  
        SqlCommand insertPurchaseOrderCommand =   
        new SqlCommand(  
        "insert into PurchaseOrders(poNumber, customerId)   
                               values(@poNumber, @customerId)");  
        insertPurchaseOrderCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        insertPurchaseOrderCommand.Parameters.Add("@customerId",   
                                         SqlDbType.VarChar, 50);  
  
        // Insert product line item.  
        SqlCommand insertProductLineItemCommand =   
             new SqlCommand("insert into ProductLineItems(productId,   
                    unitCost, quantity, poNumber) values(@productId,   
                    @unitCost, @quantity, @poNumber)");  
        insertProductLineItemCommand.Parameters.Add("@productId",   
                                           SqlDbType.VarChar, 50);  
        insertProductLineItemCommand.Parameters.Add("@unitCost",   
                                                  SqlDbType.Float);  
        insertProductLineItemCommand.Parameters.Add("@quantity",   
                                                     SqlDbType.Int);  
        insertProductLineItemCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        int rowsAffected = 0;  
        using (TransactionScope scope =   
              new TransactionScope(TransactionScopeOption.Required))  
        {  
             using (SqlConnection conn = new   
                 SqlConnection(  
                 ConfigurationManager.AppSettings["connectionString"]))  
             {  
                 conn.Open();  
  
                // Insert into purchase order table.  
               insertPurchaseOrderCommand.Connection = conn;  
               insertPurchaseOrderCommand.Parameters["@poNumber"].Value   
                                                       = po.PONumber;  
             insertPurchaseOrderCommand.Parameters["@customerId"].Value   
                                                    =po.CustomerId;  
             insertPurchaseOrderCommand.ExecuteNonQuery();  
  
            // Insert into product line item table.  
            insertProductLineItemCommand.Connection = conn;  
            foreach (PurchaseOrderLineItem orderLineItem in   
                                        po.orderLineItems) {  
            insertProductLineItemCommand.Parameters["@poNumber"].Value   
                                                          =po.PONumber;  
            insertProductLineItemCommand.Parameters["@productId"].Value   
                                             = orderLineItem.ProductId;  
            insertProductLineItemCommand.Parameters["@unitCost"].Value   
                                             = orderLineItem.UnitCost;  
            insertProductLineItemCommand.Parameters["@quantity"].Value   
                                             = orderLineItem.Quantity;  
            rowsAffected +=   
            insertProductLineItemCommand.ExecuteNonQuery();  
            }  
            scope.Complete();  
        }  
     }  
     Console.WriteLine(  
     "Updated database with {0} product line items  for purchase order   
                                     {1} ", rowsAffected, po.PONumber);  
    }  
}  
```

 <span data-ttu-id="538fa-176">일괄 처리 동작 및 구성은 서비스 응용 프로그램 구성에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-176">The batching behavior and its configuration are specified in the service application configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName"   
     value=".\private$\ServiceModelSamplesTransactedBatching" />  
    <add key="baseAddress"   
     value=  
     "http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
    <add key="connectionString" value="Data Source=.\SQLEXPRESS;AttachDbFilename=|DataDirectory|orders.mdf;Integrated Security=True;User Instance=True;" />  
  </appSettings>  
  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ThrottlingBehavior">  
          <serviceThrottling maxConcurrentCalls="5"/>  
        </behavior>  
      </serviceBehaviors>  
  
      <endpointBehaviors>  
        <behavior name="BatchingBehavior">  
          <transactedBatching maxBatchSize="100"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service   
          behaviorConfiguration="ThrottlingBehavior"   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address=  
"net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                  binding="netMsmqBinding"  
                  behaviorConfiguration="BatchingBehavior"   
                  contract=  
                    "Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="538fa-177">일괄 처리 크기는 시스템에 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-177">The batch size is a hint to the system.</span></span> <span data-ttu-id="538fa-178">예를 들어 일괄 처리 크기를 20으로 지정하면 단일 트랜잭션을 사용하여 20개의 메시지를 읽고 디스패치한 다음에 트랜잭션이 커밋됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-178">For example, if you specify a batch size of 20, then 20 messages would be read and dispatched using a single transaction and then the transaction is committed.</span></span> <span data-ttu-id="538fa-179">그러나 일괄 처리 크기에 도달하기 전에 트랜잭션에서 일괄 처리를 커밋하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-179">But there are cases where the transaction may commit the batch before the batch size is reached.</span></span>  
>   
>  <span data-ttu-id="538fa-180">트랜잭션이 생성되면 틱을 시작하는 시간 제한이 모든 트랜잭션에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-180">Associated with every transaction is a timeout that starts ticking once the transaction is created.</span></span> <span data-ttu-id="538fa-181">이 시간 제한이 만료되면 트랜잭션이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-181">When this timeout expires the transaction is aborted.</span></span> <span data-ttu-id="538fa-182">일괄 처리 크기에 도달하기 전에 이 시간 제한이 만료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-182">It is possible for this timeout to expire even before the batch size is reached.</span></span> <span data-ttu-id="538fa-183">중단으로 인해 일괄 처리 작업이 다시 실행되는 것을 방지하려면 `TransactedBatchingBehavior`에서 트랜잭션에 남은 시간을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-183">To avoid re-working the batch because of the abort, the `TransactedBatchingBehavior` checks to see how much time is left on the transaction.</span></span> <span data-ttu-id="538fa-184">트랜잭션 시간 제한의 80%가 사용되면 트랜잭션이 커밋됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-184">If 80% of the transaction timeout is used up, then the transaction is committed.</span></span>  
>   
>  <span data-ttu-id="538fa-185">큐에 메시지가 더 이상 없으면 일괄 처리 크기가 처리될 때까지 기다리지 않고 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>에서 트랜잭션을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-185">If there are no more messages in the queue then instead of waiting for the fulfillment of the batch size the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> commits the transaction.</span></span>  
>   
>  <span data-ttu-id="538fa-186">일괄 처리 크기는 응용 프로그램에 따라 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-186">The choice of the batch size is dependent on your application.</span></span> <span data-ttu-id="538fa-187">일괄 처리 크기가 너무 작으면 원하는 성능을 얻지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-187">If the batch size is too small, you may not get the desired performance.</span></span> <span data-ttu-id="538fa-188">그러나 일괄 처리 크기가 너무 크면 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-188">On the other hand if the batch size is too big, it may deteriorate performance.</span></span> <span data-ttu-id="538fa-189">예를 들어 트랜잭션을 더 길게 늘리고 데이터베이스에 잠금을 유지하거나 트랜잭션이 교착 상태가 되어 일괄 처리가 롤백되고 작업을 다시 수행하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-189">For example, your transaction could live longer and hold locks on your database or your transaction could become dead locked, which could cause the batch to get rolled back and to redo the work.</span></span>  
  
 <span data-ttu-id="538fa-190">클라이언트는 트랜잭션 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-190">The client creates a transaction scope.</span></span> <span data-ttu-id="538fa-191">트랜잭션 범위 내에서 큐와 통신을 수행하여 모든 메시지가 큐로 전송되거나 어떤 메시지도 큐로 전송되지 않는 가장 작은 단위로 처리되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-191">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages are sent to the queue or none of the messages are sent to the queue.</span></span> <span data-ttu-id="538fa-192">트랜잭션은 트랜잭션 범위에서 <xref:System.Transactions.TransactionScope.Complete%2A>를 호출하여 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-192">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A> on the transaction scope.</span></span>  

```csharp
//Client implementation code.  
class Client  
{  
    static void Main()  
    {  
        Random randomGen = new Random();  
        for (int i = 0; i < 2500; i++)  
        {  
            // Create a client with given client endpoint configuration.  
            OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
            // Create the purchase order.  
            PurchaseOrder po = new PurchaseOrder();  
            po.CustomerId = "somecustomer" + i + ".com";  
            po.PONumber = Guid.NewGuid().ToString();  
  
            PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
            lineItem1.ProductId = "Blue Widget";  
            lineItem1.Quantity = randomGen.Next(1, 100);  
            lineItem1.UnitCost = (float)randomGen.NextDouble() * 10;  
  
            PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
            lineItem2.ProductId = "Red Widget";  
            lineItem2.Quantity = 890;  
            lineItem2.UnitCost = 45.89F;  
  
            po.orderLineItems = new PurchaseOrderLineItem[2];  
            po.orderLineItems[0] = lineItem1;  
            po.orderLineItems[1] = lineItem2;  
  
            //Create a transaction scope.  
            using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
            {  
                // Make a queued call to submit the purchase order.  
                client.SubmitPurchaseOrder(po);  
                // Complete the transaction.  
                scope.Complete();  
            }  
  
            client.Close();  
        }  
        Console.WriteLine();  
        Console.WriteLine("Press <ENTER> to terminate client.");  
        Console.ReadLine();  
    }  
}  
```

 <span data-ttu-id="538fa-193">샘플을 실행하면 클라이언트 및 서비스 동작이 서비스 콘솔 창과 클라이언트 콘솔 창에 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-193">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="538fa-194">서비스에서 클라이언트가 보내는 메시지를 받는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-194">You can see the service receive messages from the client.</span></span> <span data-ttu-id="538fa-195">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-195">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="538fa-196">큐를 사용하므로 클라이언트와 서비스가 동시에 실행 중일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-196">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="538fa-197">클라이언트를 실행하고 종료한 다음 서비스를 다시 시작해도 서비스에서 계속 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-197">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span> <span data-ttu-id="538fa-198">일괄 처리에서 메시지를 읽고 처리할 때 롤링 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-198">You can see a rolling output as messages are read in a batch and processed.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Updated database with 2 product line items for purchase order 493ac832-d216-4e94-b2a5-d7f492fb5e39  
Processing Purchase Order: 8b567f5b-0661-4662-aae2-6cef1bd6d278  
        Customer: somecustomer849.com  
        OrderDetails  
               Order LineItem: 80 of Blue Widget @unit price: $9.751623  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41622.23  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 41130b95-4ea8-40a9-91c3-2e129117fcb8  
Processing Purchase Order: 5ce2699d-9a31-4cc2-a8c5-64cda614b3c7  
        Customer: somecustomer850.com  
        OrderDetails  
               Order LineItem: 89 of Blue Widget @unit price: $6.369128  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41408.95  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 8b567f5b-0661-4662-aae2-6cef1bd6d278  
Processing Purchase Order: ea94486b-7c86-4309-a42d-2f06c00656cd  
        Customer: somecustomer851.com  
        OrderDetails  
             Order LineItem: 47 of Blue Widget @unit price: $0.9391424  
             Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $40886.24  
        Order status: Pending  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="538fa-199">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="538fa-200">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="538fa-200">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="538fa-201">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="538fa-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="538fa-202">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538fa-202">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Batching`  
  
## <a name="see-also"></a><span data-ttu-id="538fa-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="538fa-203">See Also</span></span>
