---
title: "방법: 트랜잭션 서비스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bd2e4ed-a557-43f9-ba98-4c70cb75c154
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a7ef8d4778b21d33501e3f3d4478b722bf1e1cc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-transactional-service"></a><span data-ttu-id="f3002-102">방법: 트랜잭션 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="f3002-102">How to: Create a Transactional Service</span></span>
<span data-ttu-id="f3002-103">이 샘플에서는 트랜잭션 서비스 만들기의 다양한 측면과 함께, 클라이언트에서 시작한 트랜잭션을 사용하여 서비스 작업을 조정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-103">This sample demonstrates various aspects of creating a transactional service and the use of a client-initiated transaction to coordinate service operations.</span></span>  
  
### <a name="creating-a-transactional-service"></a><span data-ttu-id="f3002-104">트랜잭션 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="f3002-104">Creating a transactional service</span></span>  
  
1.  <span data-ttu-id="f3002-105">서비스 계약을 만들고 <xref:System.ServiceModel.TransactionFlowOption> 열거형에서 원하는 설정으로 작업에 주석을 추가하여 들어오는 트랜잭션의 요구 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-105">Create a service contract and annotate the operations with the desired setting from the <xref:System.ServiceModel.TransactionFlowOption> enumeration to specify the incoming transaction requirements.</span></span> <span data-ttu-id="f3002-106">구현 중인 서비스 클래스에도 <xref:System.ServiceModel.TransactionFlowAttribute>를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-106">Note that you can also place the <xref:System.ServiceModel.TransactionFlowAttribute> on the service class being implemented.</span></span> <span data-ttu-id="f3002-107">이렇게 하면 트랜잭션 설정을 모든 구현에서 사용하는 대신 단일 구현에서만 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-107">This allows for a single implementation of an interface to use these transaction settings, instead of every implementation.</span></span>  
  
    ```  
    [ServiceContract]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // Use this to require an incoming transaction  
        [TransactionFlow(TransactionFlowOption.Mandatory)]  
        double Add(double n1, double n2);  
        [OperationContract]  
        // Use this to permit an incoming transaction  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        double Subtract(double n1, double n2);  
    }  
    ```  
  
2.  <span data-ttu-id="f3002-108">구현 클래스를 만들고 <xref:System.ServiceModel.ServiceBehaviorAttribute>를 사용하여 필요한 경우 <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> 및 <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-108">Create an implementation class, and use the <xref:System.ServiceModel.ServiceBehaviorAttribute> to optionally specify a <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and a <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.</span></span> <span data-ttu-id="f3002-109">대부분의 경우 <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>의 기본값은 60초, <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>의 기본값은 `Unspecified`가 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-109">You should note that in many cases, the default <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> of 60 seconds and the default <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> of `Unspecified` are appropriate.</span></span> <span data-ttu-id="f3002-110">각 작업에 대해 <xref:System.ServiceModel.OperationBehaviorAttribute> 특성을 사용하여, 메서드 내에서 수행된 작업이 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 특성의 값에 따라 트랜잭션 범위 내에서 수행되어야 하는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-110">For each operation, you can use the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute to specify whether work performed within the method should occur within the scope of a transaction scope according to the value of the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> attribute.</span></span> <span data-ttu-id="f3002-111">이 경우 `Add` 메서드에 사용된 트랜잭션은 클라이언트로부터 들어오는 필수 트랜잭션과 동일하며, `Subtract` 메서드에 사용된 트랜잭션은 트랜잭션이 클라이언트로부터 들어오는 경우 해당 트랜잭션과 동일하며, 그렇지 않은 경우 암시적으로 로컬에서 만들어진 새 트랜잭션과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-111">In this case, the transaction used for the `Add` method is the same as the mandatory incoming transaction that is flowed from the client, and the transaction used for the `Subtract` method is either the same as the incoming transaction if one was flowed from the client, or a new implicitly and locally created transaction.</span></span>  
  
    ```  
    [ServiceBehavior(  
        TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,  
        TransactionTimeout = "00:00:45")]  
    public class CalculatorService : ICalculator  
    {  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Adding {0} to {1}", n1, n2));  
            return n1 + n2;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Subtracting {0} from {1}", n2, n1));  
            return n1 - n2;  
        }  
  
        private static void RecordToLog(string recordText)  
        {  
            // Database operations omitted for brevity  
            // This is where the transaction provides specific benefit  
            // - changes to the database will be committed only when  
            // the transaction completes.  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="f3002-112">트랜잭션 컨텍스트를 이동하도록 지정하고 이 작업에 사용할 프로토콜을 지정하여 구성 파일에서 바인딩을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-112">Configure the bindings in the configuration file, specifying that the transaction context should be flowed, and the protocols to be used to do so.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f3002-113">[ServiceModel 트랜잭션 구성](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-113"> [ServiceModel Transaction Configuration](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md).</span></span> <span data-ttu-id="f3002-114">특히 바인딩 형식은 끝점 요소의 `binding` 특성에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-114">Specifically, the binding type is specified in the endpoint element’s `binding` attribute.</span></span> <span data-ttu-id="f3002-115">[ \<끝점 >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) 요소를 포함 한 `bindingConfiguration` 이라는 바인딩 구성을 참조 하는 특성 `transactionalOleTransactionsTcpBinding`다음 샘플 구성에 표시 된 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-115">The [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element contains a `bindingConfiguration` attribute that references a binding configuration named `transactionalOleTransactionsTcpBinding`, as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     <span data-ttu-id="f3002-116">트랜잭션 흐름은 `transactionFlow` 특성을 사용하여 구성 수준에서 사용하도록 설정하며, 트랜잭션 프로토콜은 다음 구성에서처럼 `transactionProtocol` 특성을 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-116">Transaction flow is enabled at the configuration level by using the `transactionFlow` attribute, and the transaction protocol is specified using the `transactionProtocol` attribute, as shown in the following configuration.</span></span>  
  
    ```xml  
    <bindings>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="supporting-multiple-transaction-protocols"></a><span data-ttu-id="f3002-117">여러 트랜잭션 프로토콜 지원</span><span class="sxs-lookup"><span data-stu-id="f3002-117">Supporting multiple transaction protocols</span></span>  
  
1.  <span data-ttu-id="f3002-118">최적의 성능을 얻으려면 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 작성한 클라이언트 및 서비스가 관련된 시나리오의 경우 OleTransactions 프로토콜을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-118">For optimal performance, you should use the OleTransactions protocol for scenarios involving a client and service written using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="f3002-119">단, 타사 프로토콜 스택과의 상호 운용성이 필요한 시나리오의 경우에는 WS-AT(WS-AtomicTransaction) 프로토콜이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-119">However, the WS-AtomicTransaction (WS-AT) protocol is useful for scenarios when interoperability with third-party protocol stacks is required.</span></span> <span data-ttu-id="f3002-120">다음 샘플 구성처럼 여러 끝점에 해당 프로토콜별 바인딩을 제공하여 두 가지 프로토콜을 모두 허용하도록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-120">You can configure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to accept both protocols by providing multiple endpoints with appropriate protocol-specific bindings, as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="http://localhost:8000/CalcService"  
        binding="wsHttpBinding"  
        bindingConfiguration="transactionalWsatHttpBinding"  
        contract="ICalculator"  
        name="WSAtomicTransaction_endpoint" />  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     <span data-ttu-id="f3002-121">트랜잭션 프로토콜은 `transactionProtocol` 특성을 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-121">The transaction protocol is specified using the `transactionProtocol` attribute.</span></span> <span data-ttu-id="f3002-122">그러나 이 바인딩에서는 WS-AT 프로토콜만 사용할 수 있으므로 이 특성은 시스템 제공 `wsHttpBinding`에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-122">However, this attribute is absent from the system-provided `wsHttpBinding`, because this binding can only use the WS-AT protocol.</span></span>  
  
    ```xml  
    <bindings>  
      <wsHttpBinding>  
        <binding name="transactionalWsatHttpBinding"  
          transactionFlow="true" />  
      </wsHttpBinding>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="controlling-the-completion-of-a-transaction"></a><span data-ttu-id="f3002-123">트랜잭션 완료 제어</span><span class="sxs-lookup"><span data-stu-id="f3002-123">Controlling the completion of a transaction</span></span>  
  
1.  <span data-ttu-id="f3002-124">기본적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 작업은 처리되지 않은 예외가 throw되지 않으면 트랜잭션을 자동으로 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-124">By default, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] operations automatically complete transactions if no unhandled exceptions are thrown.</span></span> <span data-ttu-id="f3002-125"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> 속성 및 <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> 메서드를 사용하면 이 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-125">You can modify this behavior by using the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property and the <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> method.</span></span> <span data-ttu-id="f3002-126">debit 및 credit 연산 등 다른 연산과 동일한 트랜잭션 내에서 연산을 수행해야 하는 경우 다음 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> 연산 예제에서처럼 `false` 속성을 `Debit`로 설정하여 autocomplete 동작을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-126">When an operation is required to occur within the same transaction as another operation (for example, a debit and credit operation), you can disable the autocomplete behavior by setting the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property to `false` as shown in the following `Debit` operation example.</span></span> <span data-ttu-id="f3002-127">`Debit` 연산에서 사용하는 트랜잭션은 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> 연산에서처럼 `true`로 설정된 `Credit1` 속성을 가진 메서드가 호출될 때까지 또는 <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> 연산에서처럼 트랜잭션 완료를 명시적으로 표시하기 위해 `Credit2` 메서드가 호출될 때까지 완료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-127">The transaction the `Debit` operation uses is not completed until a method with the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property set to `true` is called, as shown in the operation `Credit1`, or when the <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> method is called to explicitly mark the transaction as complete, as shown in the operation `Credit2`.</span></span> <span data-ttu-id="f3002-128">설명의 목적으로 두 개의 credit 연산을 예로 들었지만 하나의 credit 연산이 보다 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-128">Note that the two credit operations are shown for illustration purposes, and that a single credit operation would be more typical.</span></span>  
  
    ```  
    [ServiceBehavior]  
    public class CalculatorService : IAccount  
    {  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = false)]  
        public void Debit(double n)  
        {  
            // Perform debit operation  
  
            return;  
        }  
  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = true)]  
        public void Credit1(double n)  
        {  
            // Perform credit operation  
  
            return;  
        }  
  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = false)]  
        public void Credit2(double n)  
        {  
            // Perform alternate credit operation  
  
            OperationContext.Current.SetTransactionComplete();  
            return;  
        }  
    }  
    ```  
  
2.  <span data-ttu-id="f3002-129">트랜잭션의 상관 관계를 위해 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> 속성을 `false`로 설정하려면 세션 바인딩을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-129">For the purposes of transaction correlation, setting the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property to `false` requires the use of a sessionful binding.</span></span> <span data-ttu-id="f3002-130">이 요구 사항은 `SessionMode`의 <xref:System.ServiceModel.ServiceContractAttribute> 속성을 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-130">This requirement is specified with the `SessionMode` property on the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span>  
  
    ```  
    [ServiceContract(SessionMode = SessionMode.Required)]  
    public interface IAccount  
    {  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Debit(double n);  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Credit1(double n);  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Credit2(double n);  
    }  
    ```  
  
### <a name="controlling-the-lifetime-of-a-transactional-service-instance"></a><span data-ttu-id="f3002-131">트랜잭션 서비스 인스턴스의 수명 제어</span><span class="sxs-lookup"><span data-stu-id="f3002-131">Controlling the lifetime of a transactional service instance</span></span>  
  
1.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f3002-132">에서는 <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> 속성을 사용하여 트랜잭션 완료 시 기본 서비스 인스턴스를 해제할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-132"> uses the <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> property to specify whether the underlying service instance is released when a transaction completes.</span></span> <span data-ttu-id="f3002-133">이 기본값이 `true`이기 때문에, 달리 구성하지 않는 한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 효율적이며 예상 가능한 "JIT(Just-In-Time)" 활성화 동작을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-133">Since this defaults to `true`, unless configured otherwise, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] exhibits an efficient and predictable "just-in-time" activation behavior.</span></span> <span data-ttu-id="f3002-134">후속 트랜잭션에서의 서비스에 대한 호출은 이전 트랜잭션 상태가 남아 있지 않은 새 서비스 인스턴스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-134">Calls to a service on a subsequent transaction are assured a new service instance with no remnants of the previous transaction's state.</span></span> <span data-ttu-id="f3002-135">이는 대개의 경우에 유용하지만 때로는 트랜잭션 완료와 관계없이 서비스 인스턴스 내의 상태를 유지해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-135">While this is often useful, sometimes you may want to maintain state within the service instance beyond the transaction completion.</span></span> <span data-ttu-id="f3002-136">예를 들면 필요한 상태 또는 리소스에 대한 핸들을 검색하거나 다시 구성하는 데 비용이 많이 드는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-136">Examples of this would be when required state or handles to resources are expensive to retrieve or reconstitute.</span></span> <span data-ttu-id="f3002-137"><xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> 속성을 `false`로 설정하면 서비스 인스턴스 내의 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-137">You can do this by setting the <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> property to `false`.</span></span> <span data-ttu-id="f3002-138">이렇게 설정하면 인스턴스 및 그와 관련된 모든 상태를 후속 호출에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-138">With that setting, the instance and any associated state will be available on subsequent calls.</span></span> <span data-ttu-id="f3002-139">이 설정을 사용하는 경우에는 상태 및 트랜잭션을 지우고 완료하는 시기와 방법에 대해 주의 깊게 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-139">When using this, give careful consideration to when and how state and transactions will be cleared and completed.</span></span> <span data-ttu-id="f3002-140">다음 샘플에서는 `runningTotal` 변수를 사용하여 인스턴스를 유지 관리함으로써 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-140">The following sample demonstrates how to do this by maintaining the instance with the `runningTotal` variable.</span></span>  
  
    ```  
    [ServiceBehavior(TransactionIsolationLevel = [ServiceBehavior(  
        ReleaseServiceInstanceOnTransactionComplete = false)]  
    public class CalculatorService : ICalculator  
    {  
        double runningTotal = 0;  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Adding {0} to {1}", n, runningTotal));  
            runningTotal = runningTotal + n;  
            return runningTotal;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Subtracting {0} from {1}", n, runningTotal));  
            runningTotal = runningTotal - n;  
            return runningTotal;  
        }  
  
        private static void RecordToLog(string recordText)  
        {  
            // Database operations omitted for brevity  
        }  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f3002-141">인스턴스 수명이 서비스의 내부 동작이며 <xref:System.ServiceModel.ServiceBehaviorAttribute> 속성을 통해 제어되므로, 인스턴스 동작을 설정하기 위해 서비스 구성이나 서비스 계약을 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-141">Since the instance lifetime is a behavior that is internal to the service, and controlled through the <xref:System.ServiceModel.ServiceBehaviorAttribute> property, no modification to the service configuration or service contract is required to set the instance behavior.</span></span> <span data-ttu-id="f3002-142">또한 연결에도 이에 대한 표현이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3002-142">In addition, the wire will contain no representation of this.</span></span>
