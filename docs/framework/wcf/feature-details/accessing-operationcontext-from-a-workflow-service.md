---
title: "워크플로 서비스에서 OperationContext 액세스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1dafe55-a20e-4db0-9ac8-90c315883cdd
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 11a6a1efad59ba5b9f3a143277909b63a5fe5e05
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-operationcontext-from-a-workflow-service"></a><span data-ttu-id="fe103-102">워크플로 서비스에서 OperationContext 액세스</span><span class="sxs-lookup"><span data-stu-id="fe103-102">Accessing OperationContext from a Workflow Service</span></span>
<span data-ttu-id="fe103-103">워크플로 서비스 내에서 <xref:System.ServiceModel.OperationContext>에 액세스하려면 사용자 지정 실행 속성에서 <xref:System.ServiceModel.Activities.IReceiveMessageCallback> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-103">To access the <xref:System.ServiceModel.OperationContext> inside a workflow service, you must implement the <xref:System.ServiceModel.Activities.IReceiveMessageCallback> interface in a custom execution property.</span></span> <span data-ttu-id="fe103-104">재정의 <xref:System.ServiceModel.Activities.IReceiveMessageCallback.OnReceiveMessage%2A> System.Activities.ExecutionProperties)?qualifyHint=False & autoUpgrade =에 대 한 참조를 전달 되는 True 메서드는 <xref:System.ServiceModel.OperationContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-104">Override the <xref:System.ServiceModel.Activities.IReceiveMessageCallback.OnReceiveMessage%2A> System.Activities.ExecutionProperties)?qualifyHint=False&autoUpgrade=True method which is passed a reference to the <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="fe103-105">이 항목에서는 사용자 지정 헤더를 검색하기 위해 이 실행 속성을 구현하고 런타임에 이 속성을 <xref:System.ServiceModel.Activities.Receive>에 노출할 사용자 지정 활동을 구현하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-105">This topic will walk you through implementing this execution property to retrieve a custom header, as well as a custom activity that will surface this property to the <xref:System.ServiceModel.Activities.Receive> at runtime.</span></span>  <span data-ttu-id="fe103-106">사용자 지정 활동에는 동일한 동작을 구현 합니다는 <!--zz <xref:System.ServiceModel.Activities.Sequence>--> `System.ServiceModel.Activities.Sequence` 때를 제외 하 고 활동은 <xref:System.ServiceModel.Activities.Receive> 내부에 배치는 <xref:System.ServiceModel.Activities.IReceiveMessageCallback> 호출 될 및 <xref:System.ServiceModel.OperationContext> 정보가 검색 된다는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-106">The custom activity will implement the same behavior as a <!--zz <xref:System.ServiceModel.Activities.Sequence>--> `System.ServiceModel.Activities.Sequence` activity, except that when a <xref:System.ServiceModel.Activities.Receive> is placed inside of it, the <xref:System.ServiceModel.Activities.IReceiveMessageCallback> will be called and the <xref:System.ServiceModel.OperationContext> information will be retrieved.</span></span>  <span data-ttu-id="fe103-107">이 항목에서는 클라이언트측 <xref:System.ServiceModel.OperationContext>에 액세스하여 <xref:System.ServiceModel.Activities.ISendMessageCallback> 인터페이스를 통해 나가는 헤더를 추가하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-107">This topic also shows how to access the client-side <xref:System.ServiceModel.OperationContext> to add outgoing headers via the <xref:System.ServiceModel.Activities.ISendMessageCallback> interface.</span></span>  
  
### <a name="implement-the-service-side-ireceivemessagecallback"></a><span data-ttu-id="fe103-108">서비스측 IReceiveMessageCallback 구현</span><span class="sxs-lookup"><span data-stu-id="fe103-108">Implement the Service-side IReceiveMessageCallback</span></span>  
  
1.  <span data-ttu-id="fe103-109">빈 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-109">Create an empty [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] solution.</span></span>  
  
2.  <span data-ttu-id="fe103-110">`Service`라는 새 콘솔 응용 프로그램을 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-110">Add a new console application called `Service` to the solution.</span></span>  
  
3.  <span data-ttu-id="fe103-111">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-111">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="fe103-112">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="fe103-112">System.Runtime.Serialization</span></span>  
  
    2.  <span data-ttu-id="fe103-113">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fe103-113">System.ServiceModel</span></span>  
  
    3.  <span data-ttu-id="fe103-114">System.ServiceModel.Activities</span><span class="sxs-lookup"><span data-stu-id="fe103-114">System.ServiceModel.Activities</span></span>  
  
4.  <span data-ttu-id="fe103-115">다음 예제와 같이 `ReceiveInstanceIdCallback`이라는 새 클래스를 추가하고 <xref:System.ServiceModel.Activities.IReceiveMessageCallback>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-115">Add a new class called `ReceiveInstanceIdCallback` and implement <xref:System.ServiceModel.Activities.IReceiveMessageCallback> as shown in the following example.</span></span>  
  
    ```csharp  
    class ReceiveInstanceIdCallback : IReceiveMessageCallback  
    {  
          public const string HeaderName = "InstanceIdHeader";  
          public const string HeaderNS = "http://Microsoft.Samples.AccessingOperationContext";  
  
         public void OnReceiveMessage(System.ServiceModel.OperationContext operationContext, System.Activities.ExecutionProperties activityExecutionProperties)  
          {              
                try  
                {  
                    Guid instanceId = operationContext.IncomingMessageHeaders.GetHeader<Guid>(HeaderName, HeaderNS);  
                    Console.WriteLine("Received a message from a workflow with instanceId = {0}", instanceId);  
                }  
                catch (MessageHeaderException)  
                {  
                    Console.WriteLine("This message must not be from a workflow.");  
                }  
            }  
    }  
    ```  
  
     <span data-ttu-id="fe103-116">이 코드에서는 메서드에 전달된 <xref:System.ServiceModel.OperationContext>를 사용하여 들어오는 메시지의 헤더에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-116">This code uses the <xref:System.ServiceModel.OperationContext> passed into the method to access the incoming message’s headers.</span></span>  
  
### <a name="implement-a-service-side-native-activity-to-add-the-ireceivemessagecallback-implementation-to-the-nativeactivitycontext"></a><span data-ttu-id="fe103-117">서비스측 기본 활동을 구현하여 IReceiveMessageCallback 구현을 NativeActivityContext에 추가</span><span class="sxs-lookup"><span data-stu-id="fe103-117">Implement a Service-side Native activity to add the IReceiveMessageCallback implementation to the NativeActivityContext</span></span>  
  
1.  <span data-ttu-id="fe103-118"><xref:System.Activities.NativeActivity>라는 `ReceiveInstanceIdScope`에서 파생된 새 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-118">Add a new class derived from <xref:System.Activities.NativeActivity> called `ReceiveInstanceIdScope`.</span></span>  
  
2.  <span data-ttu-id="fe103-119">자식 작업, 변수, 현재 작업 인덱스 및 <xref:System.Activities.CompletionCallback> 콜백을 추적하기 위해 로컬 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-119">Add local variables to keep track of child activities, variables, current activity index, and a <xref:System.Activities.CompletionCallback> callback.</span></span>  
  
    ```  
    public sealed class ReceiveInstanceIdScope : NativeActivity  
        {  
            Collection<Activity> children;  
            Collection<Variable> variables;  
            Variable<int> currentIndex;  
            CompletionCallback onChildComplete;  
    }  
    ```  
  
3.  <span data-ttu-id="fe103-120">생성자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-120">Implement the constructor</span></span>  
  
    ```  
    public ReceiveInstanceIdScope()  
                : base()  
            {  
                this.children = new Collection<Activity>();  
                this.variables = new Collection<Variable>();  
                this.currentIndex = new Variable<int>();  
            }  
    }  
    ```  
  
4.  <span data-ttu-id="fe103-121">`Activities` 및 `Variables` 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-121">Implement the `Activities` and `Variables` properties.</span></span>  
  
    ```  
    public Collection<Activity> Activities  
    {  
         get { return this.children; }  
    }  
  
    public Collection<Variable> Variables  
    {  
        get { return this.variables; }  
    }  
    ```  
  
5.  <span data-ttu-id="fe103-122"><xref:System.Activities.NativeActivity.CacheMetadata%2A>를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-122">Override <xref:System.Activities.NativeActivity.CacheMetadata%2A></span></span>  
  
    ```  
    protected override void CacheMetadata(NativeActivityMetadata metadata)  
    {  
        //call base.CacheMetadata to add the Activities and Variables to this activity's metadata  
        base.CacheMetadata(metadata);  
        //add the private implementation variable: currentIndex   
        metadata.AddImplementationVariable(this.currentIndex);  
    }  
    ```  
  
6.  <span data-ttu-id="fe103-123"><xref:System.Activities.NativeActivity.Execute%2A>를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-123">Override <xref:System.Activities.NativeActivity.Execute%2A></span></span>  
  
    ```  
    protected override void Execute(  
                NativeActivityContext context)  
            {  
                context.Properties.Add("ReceiveInstanceIdCallback", new ReceiveInstanceIdCallback());  
                InternalExecute(context, null);  
            }  
  
            void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
            {  
                //grab the index of the current Activity  
                int currentActivityIndex = this.currentIndex.Get(context);  
                if (currentActivityIndex == Activities.Count)  
                {  
                    //if the currentActivityIndex is equal to the count of MySequence's Activities  
                    //MySequence is complete  
                    return;  
                }  
  
                if (this.onChildComplete == null)  
                {  
                    //on completion of the current child, have the runtime call back on this method  
                    this.onChildComplete = new CompletionCallback(InternalExecute);  
                }  
  
                //grab the next Activity in MySequence.Activities and schedule it  
                Activity nextChild = Activities[currentActivityIndex];  
                context.ScheduleActivity(nextChild, this.onChildComplete);  
  
                //increment the currentIndex  
                this.currentIndex.Set(context, ++currentActivityIndex);  
            }  
    ```  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="fe103-124">워크플로 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="fe103-124">Implement the workflow service</span></span>  
  
1.  <span data-ttu-id="fe103-125">기존 열 `Program` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-125">Open the existing `Program` class.</span></span>  
  
2.  <span data-ttu-id="fe103-126">다음 상수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-126">Define the following constants:</span></span>  
  
    ```  
    class Program  
    {  
       const string addr = "http://localhost:8080/Service";  
       static XName contract = XName.Get("IService", "http://tempuri.org");  
    }  
    ```  
  
3.  <span data-ttu-id="fe103-127">워크플로 서비스를 만드는 `GetWorkflowService`라는 정적 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-127">Add a static method called `GetWorkflowService` that creates the workflow service.</span></span>  
  
    ```  
    static Activity GetServiceWorkflow()  
            {  
                Variable<string> echoString = new Variable<string>();  
  
                Receive echoRequest = new Receive  
                {  
                    CanCreateInstance = true,  
                    ServiceContractName = contract,  
                    OperationName = "Echo",  
                    Content = new ReceiveParametersContent()  
                    {  
                        Parameters = { { "echoString", new OutArgument<string>(echoString) } }  
                    }  
                };  
  
                return new ReceiveInstanceIdScope  
                {  
                    Variables = { echoString },  
                    Activities =  
                    {  
                        echoRequest,  
                        new WriteLine { Text = new InArgument<string>( (e) => "Received: " + echoString.Get(e) ) },  
                        new SendReply  
                        {  
                            Request = echoRequest,  
                            Content = new SendParametersContent()  
                            {  
                                Parameters = { { "result", new InArgument<string>(echoString) } }   
                            }  
                        }  
                    }  
                };  
            }  
    ```  
  
4.  <span data-ttu-id="fe103-128">기존 `Main` 메서드에서 워크플로 서비스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-128">In the existing `Main` method, host the workflow service.</span></span>  
  
    ```  
    static void Main(string[] args)  
            {  
                string addr = "http://localhost:8080/Service";  
  
                using (WorkflowServiceHost host = new WorkflowServiceHost(GetServiceWorkflow()))  
                {  
                    host.AddServiceEndpoint(contract, new BasicHttpBinding(), addr);  
  
                    host.Open();  
                    Console.WriteLine("Service waiting at: " + addr);  
                    Console.WriteLine("Press [ENTER] to exit");  
                    Console.ReadLine();  
                    host.Close();  
                }  
            }  
    ```  
  
### <a name="implement-the-client-side-isendmessagecallback"></a><span data-ttu-id="fe103-129">클라이언트측 ISendMessageCallback 구현</span><span class="sxs-lookup"><span data-stu-id="fe103-129">Implement the Client-side ISendMessageCallback</span></span>  
  
1.  <span data-ttu-id="fe103-130">`Service`라는 새 콘솔 응용 프로그램을 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-130">Add a new console application called `Service` to the solution.</span></span>  
  
2.  <span data-ttu-id="fe103-131">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-131">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="fe103-132">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="fe103-132">System.Runtime.Serialization</span></span>  
  
    2.  <span data-ttu-id="fe103-133">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fe103-133">System.ServiceModel</span></span>  
  
    3.  <span data-ttu-id="fe103-134">System.ServiceModel.Activities</span><span class="sxs-lookup"><span data-stu-id="fe103-134">System.ServiceModel.Activities</span></span>  
  
3.  <span data-ttu-id="fe103-135">다음 예제와 같이 `SendInstanceIdCallback`이라는 새 클래스를 추가하고 <xref:System.ServiceModel.Activities.ISendMessageCallback>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-135">Add a new class called `SendInstanceIdCallback` and implement <xref:System.ServiceModel.Activities.ISendMessageCallback> as shown in the following example.</span></span>  
  
    ```csharp  
    class SendInstanceIdCallback : ISendMessageCallback  
        {  
            public const string HeaderName = "InstanceIdHeader";  
            public const string HeaderNS = "http://Microsoft.Samples.AccessingOperationContext";  
  
            public Guid InstanceId { get; set; }  
  
            public void OnSendMessage(System.ServiceModel.OperationContext operationContext)  
            {  
                operationContext.OutgoingMessageHeaders.Add(MessageHeader.CreateHeader(HeaderName, HeaderNS, this.InstanceId));  
            }  
        }  
    ```  
  
     <span data-ttu-id="fe103-136">이 코드에서는 메서드에 전달된 <xref:System.ServiceModel.OperationContext>를 사용하여 사용자 지정 헤더를 들어오는 메시지에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-136">This code uses the <xref:System.ServiceModel.OperationContext> passed into the method to add a custom header to the incoming message.</span></span>  
  
### <a name="implement-a-client-side-native-activity-to-add-the-client-side-isendmessagecallback-implementation-to-the-nativeactivitycontext"></a><span data-ttu-id="fe103-137">클라이언트측 기본 활동을 구현하여 클라이언트측 ISendMessageCallback 구현을 NativeActivityContext에 추가</span><span class="sxs-lookup"><span data-stu-id="fe103-137">Implement a Client-side Native activity to add the client-side ISendMessageCallback implementation to the NativeActivityContext</span></span>  
  
1.  <span data-ttu-id="fe103-138"><xref:System.Activities.NativeActivity>라는 `SendInstanceIdScope`에서 파생된 새 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-138">Add a new class derived from <xref:System.Activities.NativeActivity> called `SendInstanceIdScope`.</span></span>  
  
2.  <span data-ttu-id="fe103-139">자식 작업, 변수, 현재 작업 인덱스 및 <xref:System.Activities.CompletionCallback> 콜백을 추적하기 위해 로컬 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-139">Add local variables to keep track of child activities, variables, current activity index, and a <xref:System.Activities.CompletionCallback> callback.</span></span>  
  
    ```  
    public sealed class SendInstanceIdScope : NativeActivity  
        {  
            Collection<Activity> children;  
            Collection<Variable> variables;  
            Variable<int> currentIndex;  
            CompletionCallback onChildComplete;  
    }  
    ```  
  
3.  <span data-ttu-id="fe103-140">생성자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-140">Implement the constructor</span></span>  
  
    ```  
    public SendInstanceIdScope()  
                : base()  
            {  
                this.children = new Collection<Activity>();  
                this.variables = new Collection<Variable>();  
                this.currentIndex = new Variable<int>();  
            }  
    ```  
  
4.  <span data-ttu-id="fe103-141">`Activities` 및 `Variables` 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-141">Implement the `Activities` and `Variables` properties.</span></span>  
  
    ```  
    public Collection<Activity> Activities  
    {  
         get { return this.children; }  
    }  
  
    public Collection<Variable> Variables  
    {  
        get { return this.variables; }  
    }  
    ```  
  
5.  <span data-ttu-id="fe103-142"><xref:System.Activities.NativeActivity.CacheMetadata%2A>를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-142">Override <xref:System.Activities.NativeActivity.CacheMetadata%2A></span></span>  
  
    ```  
    protected override void CacheMetadata(NativeActivityMetadata metadata)  
    {  
        //call base.CacheMetadata to add the Activities and Variables to this activity's metadata  
        base.CacheMetadata(metadata);  
        //add the private implementation variable: currentIndex   
        metadata.AddImplementationVariable(this.currentIndex);  
    }  
    ```  
  
6.  <span data-ttu-id="fe103-143"><xref:System.Activities.NativeActivity.Execute%2A>를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-143">Override <xref:System.Activities.NativeActivity.Execute%2A></span></span>  
  
    ```  
    protected override void Execute(  
                NativeActivityContext context)  
            {  
                context.Properties.Add("SendInstanceIdCallback", new SendInstanceIdCallback() { InstanceId = context.WorkflowInstanceId });  
                InternalExecute(context, null);  
            }  
  
            void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
            {  
                //grab the index of the current Activity  
                int currentActivityIndex = this.currentIndex.Get(context);  
                if (currentActivityIndex == Activities.Count)  
                {  
                    //if the currentActivityIndex is equal to the count of MySequence's Activities  
                    //MySequence is complete  
                    return;  
                }  
  
                if (this.onChildComplete == null)  
                {  
                    //on completion of the current child, have the runtime call back on this method  
                    this.onChildComplete = new CompletionCallback(InternalExecute);  
                }  
  
                //grab the next Activity in MySequence.Activities and schedule it  
                Activity nextChild = Activities[currentActivityIndex];  
                context.ScheduleActivity(nextChild, this.onChildComplete);  
  
                //increment the currentIndex  
                this.currentIndex.Set(context, ++currentActivityIndex);  
            }  
    protected override void Execute(  
                NativeActivityContext context)  
            {  
                context.Properties.Add("ReceiveInstanceIdCallback", new ReceiveInstanceIdCallback());  
                InternalExecute(context, null);  
            }  
  
            void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
            {  
                //grab the index of the current Activity  
                int currentActivityIndex = this.currentIndex.Get(context);  
                if (currentActivityIndex == Activities.Count)  
                {  
                    //if the currentActivityIndex is equal to the count of MySequence's Activities  
                    //MySequence is complete  
                    return;  
                }  
  
                if (this.onChildComplete == null)  
                {  
                    //on completion of the current child, have the runtime call back on this method  
                    this.onChildComplete = new CompletionCallback(InternalExecute);  
                }  
  
                //grab the next Activity in MySequence.Activities and schedule it  
                Activity nextChild = Activities[currentActivityIndex];  
                context.ScheduleActivity(nextChild, this.onChildComplete);  
  
                //increment the currentIndex  
                this.currentIndex.Set(context, ++currentActivityIndex);  
            }  
    ```  
  
### <a name="implement-a-workflow-client"></a><span data-ttu-id="fe103-144">워크플로 클라이언트 구현</span><span class="sxs-lookup"><span data-stu-id="fe103-144">Implement a workflow client</span></span>  
  
1.  <span data-ttu-id="fe103-145">`Client`라는 콘솔 응용 프로그램 프로젝트를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-145">Create a new console application project called `Client`.</span></span>  
  
2.  <span data-ttu-id="fe103-146">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-146">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="fe103-147">System.Activities</span><span class="sxs-lookup"><span data-stu-id="fe103-147">System.Activities</span></span>  
  
    2.  <span data-ttu-id="fe103-148">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fe103-148">System.ServiceModel</span></span>  
  
    3.  <span data-ttu-id="fe103-149">System.ServiceModel.Activities</span><span class="sxs-lookup"><span data-stu-id="fe103-149">System.ServiceModel.Activities</span></span>  
  
3.  <span data-ttu-id="fe103-150">생성된 Program.cs 파일을 열고 `GetClientWorkflow`라는 정적 메서드를 추가하여 클라이언트 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-150">Open the generated Program.cs file and add a static method called `GetClientWorkflow` to create the client workflow.</span></span>  
  
    ```  
    static Activity GetClientWorkflow()  
            {  
                Variable<string> echoString = new Variable<string>();  
  
                // Define the endpoint  
                Endpoint clientEndpoint = new Endpoint  
                {  
                    Binding = new BasicHttpBinding(),  
                    AddressUri = new Uri("http://localhost:8080/Service")  
                };  
  
                // Configure the Send activity used to send a message  
                Send echoRequest = new Send  
                {  
                    Endpoint = clientEndpoint,  
                    ServiceContractName = XName.Get("IService", "http://tempuri.org"),  
                    OperationName = "Echo",  
                    Content = new SendParametersContent()  
                    {  
                        Parameters = { { "echoString", new InArgument<string>("Hello, World") } }   
                    }  
                };  
  
                // Place the Send activity in a SendInstanceIdScope. This hooks up the ISendMessageCallback   
                // implementation to the client workflow.  
                return new SendInstanceIdScope  
                {  
                    Variables = { echoString },  
                    Activities =  
                    {                      
                        new CorrelationScope  
                        {  
                            Body = new Sequence  
                            {  
                                Activities =   
                                {  
                                    // Send the request message  
                                    echoRequest,  
  
                                   // Receive the reply from the service  
                                    new ReceiveReply  
                                    {  
                                        Request = echoRequest,  
                                        Content = new ReceiveParametersContent  
                                        {  
                                            Parameters = { { "result", new OutArgument<string>(echoString) } }  
                                        }  
                                    }  
                                }  
                            }  
                        },                      
                        new WriteLine { Text = new InArgument<string>( (e) => "Received Text: " + echoString.Get(e) ) },                      
                    }  
                };  
            }  
    ```  
  
4.  <span data-ttu-id="fe103-151">다음 호스팅 코드를 `Main()` 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-151">Add the following hosting code to the `Main()` method.</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
       Activity workflow = GetClientWorkflow();  
       WorkflowInvoker.Invoke(workflow);  
       WorkflowInvoker.Invoke(workflow);  
       Console.WriteLine("Press [ENTER] to exit");  
       Console.ReadLine();  
    }  
    ```  
  
## <a name="example"></a><span data-ttu-id="fe103-152">예제</span><span class="sxs-lookup"><span data-stu-id="fe103-152">Example</span></span>  
 <span data-ttu-id="fe103-153">다음은 이 항목에서 사용되는 전체 소스 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-153">Here is a complete listing of the source code used in this topic.</span></span>  
  
```  
// ReceiveInstanceIdScope.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System.Activities;  
using System.Collections.ObjectModel;  
  
namespace Microsoft.Samples.AccessingOperationContext.Service  
{  
    public sealed class ReceiveInstanceIdScope : NativeActivity  
    {  
        Collection<Activity> children;  
        Collection<Variable> variables;  
        Variable<int> currentIndex;  
        CompletionCallback onChildComplete;  
  
        public ReceiveInstanceIdScope()  
            : base()  
        {  
            this.children = new Collection<Activity>();  
            this.variables = new Collection<Variable>();  
            this.currentIndex = new Variable<int>();  
        }  
  
        public Collection<Activity> Activities  
        {  
            get  
            {  
                return this.children;  
            }  
        }  
  
        public Collection<Variable> Variables  
        {  
            get  
            {  
                return this.variables;  
            }  
        }  
  
        protected override void CacheMetadata(NativeActivityMetadata metadata)  
        {  
            //call base.CacheMetadata to add the Activities and Variables to this activity's metadata  
            base.CacheMetadata(metadata);  
            //add the private implementation variable: currentIndex   
            metadata.AddImplementationVariable(this.currentIndex);  
        }                     
  
        protected override void Execute(  
            NativeActivityContext context)  
        {  
            context.Properties.Add("ReceiveInstanceIdCallback", new ReceiveInstanceIdCallback());  
            InternalExecute(context, null);  
        }  
  
        void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
        {  
            //grab the index of the current Activity  
            int currentActivityIndex = this.currentIndex.Get(context);  
            if (currentActivityIndex == Activities.Count)  
            {  
                //if the currentActivityIndex is equal to the count of MySequence's Activities  
                //MySequence is complete  
                return;  
            }  
  
            if (this.onChildComplete == null)  
            {  
                //on completion of the current child, have the runtime call back on this method  
                this.onChildComplete = new CompletionCallback(InternalExecute);  
            }  
  
            //grab the next Activity in MySequence.Activities and schedule it  
            Activity nextChild = Activities[currentActivityIndex];  
            context.ScheduleActivity(nextChild, this.onChildComplete);  
  
            //increment the currentIndex  
            this.currentIndex.Set(context, ++currentActivityIndex);  
        }  
    }  
}  
```  
  
```  
// ReceiveInstanceIdScope.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.ServiceModel;  
using System.ServiceModel.Activities;  
  
namespace Microsoft.Samples.AccessingOperationContext.Service  
{  
    class ReceiveInstanceIdCallback : IReceiveMessageCallback  
    {  
        public const string HeaderName = "InstanceIdHeader";  
        public const string HeaderNS = "http://Microsoft.Samples.AccessingOperationContext";  
  
        public void OnReceiveMessage(System.ServiceModel.OperationContext operationContext, System.Activities.ExecutionProperties activityExecutionProperties)  
        {              
            try  
            {  
                Guid instanceId = operationContext.IncomingMessageHeaders.GetHeader<Guid>(HeaderName, HeaderNS);  
                Console.WriteLine("Received a message from a workflow with instanceId = {0}", instanceId);  
            }  
            catch (MessageHeaderException)  
            {  
                Console.WriteLine("This message must not be from a workflow.");  
            }  
        }  
    }  
}  
```  
  
```  
// Service.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.Activities;  
using System.Activities.Statements;  
using System.ServiceModel;  
using System.ServiceModel.Activities;  
using System.Xml.Linq;  
  
namespace Microsoft.Samples.AccessingOperationContext.Service  
{      
    class Program  
    {  
        const string addr = "http://localhost:8080/Service";  
        static XName contract = XName.Get("IService", "http://tempuri.org");  
  
        static void Main(string[] args)  
        {  
            string addr = "http://localhost:8080/Service";  
  
            using (WorkflowServiceHost host = new WorkflowServiceHost(GetServiceWorkflow()))  
            {  
                host.AddServiceEndpoint(contract, new BasicHttpBinding(), addr);  
  
                host.Open();  
                Console.WriteLine("Service waiting at: " + addr);  
                Console.WriteLine("Press [ENTER] to exit");  
                Console.ReadLine();  
                host.Close();  
            }  
  
        }  
  
        static Activity GetServiceWorkflow()  
        {  
            Variable<string> echoString = new Variable<string>();  
  
            Receive echoRequest = new Receive  
            {  
                CanCreateInstance = true,  
                ServiceContractName = contract,  
                OperationName = "Echo",  
                Content = new ReceiveParametersContent()  
                {  
                    Parameters = { { "echoString", new OutArgument<string>(echoString) } }  
                }  
            };  
  
            return new ReceiveInstanceIdScope  
            {  
                Variables = { echoString },  
                Activities =  
                {  
                    echoRequest,  
                    new WriteLine { Text = new InArgument<string>( (e) => "Received: " + echoString.Get(e) ) },  
                    new SendReply  
                    {  
                        Request = echoRequest,  
                        Content = new SendParametersContent()  
                        {  
                            Parameters = { { "result", new InArgument<string>(echoString) } }   
                        }  
                    }  
                }  
            };  
        }  
    }  
  
}  
```  
  
```  
// SendInstanceIdCallback.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Channels;  
  
namespace Microsoft.Samples.AccessingOperationContext.Client  
{  
    class SendInstanceIdCallback : ISendMessageCallback  
    {  
        public const string HeaderName = "InstanceIdHeader";  
        public const string HeaderNS = "http://Microsoft.Samples.AccessingOperationContext";  
  
        public Guid InstanceId { get; set; }  
  
        public void OnSendMessage(System.ServiceModel.OperationContext operationContext)  
        {  
            operationContext.OutgoingMessageHeaders.Add(MessageHeader.CreateHeader(HeaderName, HeaderNS, this.InstanceId));  
        }  
    }  
}  
```  
  
```  
// SendInstanceIdScope.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System.Activities;  
using System.Collections.ObjectModel;  
  
namespace Microsoft.Samples.AccessingOperationContext.Client  
{  
    public sealed class SendInstanceIdScope : NativeActivity  
    {  
        Collection<Activity> children;  
        Collection<Variable> variables;  
        Variable<int> currentIndex;  
        CompletionCallback onChildComplete;  
  
        public SendInstanceIdScope()  
            : base()  
        {  
            this.children = new Collection<Activity>();  
            this.variables = new Collection<Variable>();  
            this.currentIndex = new Variable<int>();  
        }  
  
        public Collection<Activity> Activities  
        {  
            get  
            {  
                return this.children;  
            }  
        }  
  
        public Collection<Variable> Variables  
        {  
            get  
            {  
                return this.variables;  
            }  
        }  
  
        protected override void CacheMetadata(NativeActivityMetadata metadata)  
        {  
            //call base.CacheMetadata to add the Activities and Variables to this activity's metadata  
            base.CacheMetadata(metadata);  
            //add the private implementation variable: currentIndex   
            metadata.AddImplementationVariable(this.currentIndex);  
        }  
  
        protected override void Execute(  
            NativeActivityContext context)  
        {  
            context.Properties.Add("SendInstanceIdCallback", new SendInstanceIdCallback() { InstanceId = context.WorkflowInstanceId });  
            InternalExecute(context, null);  
        }  
  
        void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
        {  
            //grab the index of the current Activity  
            int currentActivityIndex = this.currentIndex.Get(context);  
            if (currentActivityIndex == Activities.Count)  
            {  
                //if the currentActivityIndex is equal to the count of MySequence's Activities  
                //MySequence is complete  
                return;  
            }  
  
            if (this.onChildComplete == null)  
            {  
                //on completion of the current child, have the runtime call back on this method  
                this.onChildComplete = new CompletionCallback(InternalExecute);  
            }  
  
            //grab the next Activity in MySequence.Activities and schedule it  
            Activity nextChild = Activities[currentActivityIndex];  
            context.ScheduleActivity(nextChild, this.onChildComplete);  
  
            //increment the currentIndex  
            this.currentIndex.Set(context, ++currentActivityIndex);  
        }  
    }  
}  
```  
  
```  
// Client.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.Activities;  
using System.Activities.Statements;  
using System.ServiceModel;  
using System.ServiceModel.Activities;  
using System.Xml.Linq;  
  
namespace Microsoft.Samples.AccessingOperationContext.Client  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Activity workflow = GetClientWorkflow();  
            WorkflowInvoker.Invoke(workflow);  
            WorkflowInvoker.Invoke(workflow);  
            Console.WriteLine("Press [ENTER] to exit");  
            Console.ReadLine();  
        }  
  
        static Activity GetClientWorkflow()  
        {  
            Variable<string> echoString = new Variable<string>();  
  
            Endpoint clientEndpoint = new Endpoint  
            {  
                Binding = new BasicHttpBinding(),  
                AddressUri = new Uri("http://localhost:8080/Service")  
            };  
  
            Send echoRequest = new Send  
            {  
                Endpoint = clientEndpoint,  
                ServiceContractName = XName.Get("IService", "http://tempuri.org"),  
                OperationName = "Echo",  
                Content = new SendParametersContent()  
                {  
                    Parameters = { { "echoString", new InArgument<string>("Hello, World") } }   
                }  
            };  
  
            return new SendInstanceIdScope  
            {  
                Variables = { echoString },  
                Activities =  
                {                      
                    new CorrelationScope  
                    {  
                        Body = new Sequence  
                        {  
                            Activities =   
                            {  
                                echoRequest,  
                                new ReceiveReply  
                                {  
                                    Request = echoRequest,  
                                    Content = new ReceiveParametersContent  
                                    {  
                                        Parameters = { { "result", new OutArgument<string>(echoString) } }  
                                    }  
                                }  
                            }  
                        }  
                    },                      
                    new WriteLine { Text = new InArgument<string>( (e) => "Received Text: " + echoString.Get(e) ) },                      
                }  
            };  
        }  
    }  
}  
```  
  
 <span data-ttu-id="fe103-154">선택적 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="fe103-154">Optional comments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe103-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe103-155">See Also</span></span>  
 [<span data-ttu-id="fe103-156">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="fe103-156">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="fe103-157">OperationContext 액세스</span><span class="sxs-lookup"><span data-stu-id="fe103-157">Accessing OperationContext</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/accessing-operationcontext.md)  
 [<span data-ttu-id="fe103-158">명령형 코드를 사용하여 워크플로, 활동 및 식 작성</span><span class="sxs-lookup"><span data-stu-id="fe103-158">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](../../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)
