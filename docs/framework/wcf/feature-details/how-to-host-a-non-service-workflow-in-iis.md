---
title: '방법: IIS에서 서비스가 아닌 워크플로 호스팅'
ms.date: 03/30/2017
ms.assetid: f362562c-767d-401b-8257-916616568fd4
ms.openlocfilehash: 70fd6aca94f2addd7ee568e897171ae1da86db67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496761"
---
# <a name="how-to-host-a-non-service-workflow-in-iis"></a>방법: IIS에서 서비스가 아닌 워크플로 호스팅
워크플로 서비스가 아닌 워크플로는 IIS/WAS에서 호스트될 수 있습니다. 이는 다른 사람이 작성한 워크플로를 호스트해야 하는 경우에 유용합니다. Workflow Designer를 다시 호스트하고 사용자가 워크플로를 직접 만들 수 있도록 허용하는 경우를 예로 들 수 있습니다.  IIS에서 서비스가 아닌 워크플로를 호스트하면 프로세스 재활용, 유휴 상태이면 종료, 프로세스 상태 모니터링 및 메시지 기반 활성화와 같은 기능이 지원됩니다. IIS에서 호스트되는 워크플로 서비스에는 <xref:System.ServiceModel.Activities.Receive> 활동이 포함되고 IIS에서 메시지가 수신되면 서비스가 활성화됩니다. 서비스가 아닌 워크플로에는 메시징 활동이 포함되지 않으며 기본적으로 메시지 전송을 통해 활성화할 수 없습니다.  <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>에서 클래스를 파생하고 워크플로 인스턴스를 만드는 작업이 포함된 서비스 계약을 정의해야 합니다. 이 항목에서는 간단한 워크플로 만드는에서 워크플로 활성화 하기 위해 클라이언트가 사용할 수는 서비스 계약을 정의 및에서 클래스를 파생 하는 과정을 안내 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> 워크플로 만들기 요청에 대 한 수신 하도록 서비스 계약을 사용 하 여입니다.  
  
### <a name="create-a-simple-workflow"></a>간단한 워크플로 만들기  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]라는 비어 있는 새 `CreationEndpointTest` 솔루션을 만듭니다.  
  
2.  `SimpleWorkflow`라는 새 WCF 워크플로 서비스 응용 프로그램 프로젝트를 솔루션에 추가합니다. Workflow Designer가 열립니다.  
  
3.  ReceiveRequest 및 SendResponse 활동을 삭제합니다. 이러한 활동은 워크플로를 워크플로 서비스로 만듭니다. 워크플로 서비스로 작업하는 것이 아니므로 이러한 활동이 더 이상 필요하지 않습니다.  
  
4.  시퀀스 활동을 "Sequential Workflow" DisplayName을 설정 합니다.  
  
5.  Service1.xamlx의 이름을 Workflow1.xamlx로 바꿉니다.  
  
6.  Sequence 활동 외부에서 디자이너를 클릭 하 고 Name 및 ConfigurationName 속성을 "workflow1"로 설정  
  
7.  <xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.Activities.Statements.Sequence>로 끌어 옵니다. <xref:System.Activities.Statements.WriteLine> 에서 활동을 확인할 수 있습니다는 **기본 형식** 도구 상자의 섹션. 설정의 <xref:System.Activities.Statements.WriteLine.Text%2A> 의 속성은 <xref:System.Activities.Statements.WriteLine> 활동을 "Hello, world"입니다.  
  
     그러면 워크플로가 다음 다이어그램과 같이 표시됩니다.  
  
     ![간단한 워크플로](../../../../docs/framework/wcf/feature-details/media/simpleworkflow.png "SimpleWorkflow")  
  
### <a name="create-the-workflow-creation-service-contract"></a>워크플로 생성 서비스 계약 만들기  
  
1.  `Shared`라는 새 클래스 라이브러리 프로젝트를 `CreationEndpointTest` 솔루션에 추가합니다.  
  
2.  System.ServiceModel.dll, System.Configuration 및 System.ServiceModel.Activities에 대한 참조를 `Shared` 프로젝트에 추가합니다.  
  
3.  Class1.cs 파일의 이름을 IWorkflowCreation.cs로 바꾸고 다음 코드를 이 파일에 추가합니다.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
  
    namespace Shared  
    {  
        //service contract exposed from the endpoint  
        [ServiceContract(Name = "IWorkflowCreation")]  
        public interface IWorkflowCreation  
        {  
            [OperationContract(Name = "Create")]  
            Guid Create(IDictionary<string, object> inputs);  
  
            [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
            void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
        }  
    }  
    ```  
  
     이 계약은 두 작업을 정의합니다. 두 작업 모두 방금 만든 서비스가 아닌 워크플로의 새 인스턴스를 만듭니다. 한 작업은 생성된 인스턴스 ID를 사용하여 새 인스턴스를 만들고 다른 작업은 새 워크플로 인스턴스의 인스턴스 ID를 지정할 수 있도록 합니다.  두 방법 모두 새 워크플로 인스턴스에 매개 변수를 전달할 수 있습니다. 이 계약에서 노출 될는 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> 클라이언트가 서비스가 아닌 워크플로의 새 인스턴스를 만들 수 있도록 합니다.  
  
### <a name="derive-a-class-from-workflowhostingendpoint"></a>WorkflowHostingEndpoint에서 클래스 파생  
  
1.  라는 새 클래스 추가 `CreationEndpoint` 에서 파생 된 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> 에 `Shared` 프로젝트.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Globalization;  
    using System.ServiceModel;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Channels;  
  
    namespace Shared  
    {  
        public class CreationEndpoint : WorkflowHostingEndpoint  
        {  
        }  
    }  
    ```  
  
2.  <xref:System.Uri>라는 로컬 정적 `defaultBaseUri` 변수를 `CreationEndpoint` 클래스에 추가합니다.  
  
    ```  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
    }  
    ```  
  
3.  `CreationEndpoint` 클래스에 다음 생성자를 추가합니다. 기본 생성자 호출에는 `IWorkflowCreation` 서비스 계약을 지정합니다.  
  
    ```  
    public CreationEndpoint(Binding binding, EndpointAddress address)  
       : base(typeof(IWorkflowCreation), binding, address)  
       {  
       }  
    ```  
  
4.  `CreationEndpoint` 클래스에 다음 기본 생성자를 추가합니다.  
  
    ```  
    public CreationEndpoint()  
       : this(GetDefaultBinding(),  
       new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative))))  
       {  
       }  
    ```  
  
5.  `DefaultBaseUri` 클래스에 정적 `CreationEndpoint` 속성을 추가합니다. 이 속성은 기본적인 기본 URI가 제공되지 않은 경우 기본 URI를 저장하는 데 사용됩니다.  
  
    ```  
    static Uri DefaultBaseUri  
    {  
       get  
       {  
          if (defaultBaseUri == null)  
          {  
             defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                Process.GetCurrentProcess().Id,  
                AppDomain.CurrentDomain.Id));  
          }  
          return defaultBaseUri;  
       }  
     }  
    ```  
  
6.  만들기 끝점에 사용할 기본 바인딩을 가져오는 다음 메서드를 만듭니다.  
  
    ```  
    //defaults to NetNamedPipeBinding  
    public static Binding GetDefaultBinding()  
    {  
       return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
    }  
    ```  
  
7.  워크플로 인스턴스 ID를 반환하도록 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A> 메서드를 재정의합니다. 경우는 `Action` 경우 빈 GUID를 반환 하는 "만들기"로 `Action` 헤더가 "CreateWithInstanceId" 반환 메서드에 전달 된 GUID로 끝납니다. 그 외의 경우에는 <xref:System.InvalidOperationException>을 throw합니다. 이러한 `Action` 헤더는 `IWorkflowCreation` 서비스 계약에 정의된 두 작업에 해당합니다.  
  
    ```  
    protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
    {  
       //Create was called by client  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
       {  
          return Guid.Empty;  
       }  
       //CreateWithInstanceId was called by client  
       else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
       {  
          return (Guid)inputs[1];  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
    }  
    ```  
  
8.  <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A>를 만들고 워크플로의 모든 인수를 추가한 다음 클라이언트에 인스턴스 ID를 보내고 <xref:System.ServiceModel.Activities.WorkflowCreationContext>를 반환하도록 <xref:System.ServiceModel.Activities.WorkflowCreationContext> 메서드를 재정의합니다.  
  
    ```  
    protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
    {  
       WorkflowCreationContext creationContext = new WorkflowCreationContext();  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create") || (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId")))  
       {  
          Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
          if (arguments != null && arguments.Count > 0)  
          {  
             foreach (KeyValuePair<string, object> pair in arguments)  
             {  
                //arguments to pass to the workflow  
                creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
             }  
          }  
          //reply to client with instanceId  
          responseContext.SendResponse(instanceId, null);  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
       return creationContext;  
    }  
    ```  
  
### <a name="create-a-standard-endpoint-element-to-allow-you-to-configure-the-workflowcreationendpoint"></a>WorkflowCreationEndpoint를 구성할 수 있도록 표준 끝점 요소 만들기  
  
1.  `CreationEndpoint` 프로젝트에서 Shared에 대한 참조를 추가합니다.  
  
2.  `CreationEndpointElement`에서 파생된 <xref:System.ServiceModel.Configuration.StandardEndpointElement>라는 새 클래스를 `CreationEndpoint` 프로젝트에 추가합니다. 이 클래스는 web.config 파일의 `CreationEndpoint`를 나타냅니다.  
  
    ```  
    using System;  
    using System.Configuration;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Configuration;  
    using System.ServiceModel.Description;  
    using Shared;  
  
    namespace CreationEndpointTest  
    {  
        //config element for CreationEndpoint  
        public class CreationEndpointElement : StandardEndpointElement  
        {  
       }  
    ```  
  
3.  끝점의 형식을 반환하기 위해 `EndpointType`이라는 속성을 추가합니다.  
  
    ```  
    protected override Type EndpointType  
    {  
       get { return typeof(CreationEndpoint); }  
    }  
    ```  
  
4.  <xref:System.ServiceModel.Configuration.StandardEndpointElement.CreateServiceEndpoint%2A> 메서드를 재정의하고 새 `CreationEndpoint`를 반환합니다.  
  
    ```  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
    {  
       return new CreationEndpoint();  
    }  
    ```  
  
5.  <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> 및 <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> 메서드를 오버로드합니다. 이러한 메서드는 정의되어야 하며 이러한 메서드에 코드를 추가할 필요는 없습니다.  
  
    ```  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
    ```  
  
6.  `CreationEndpoint`의 컬렉션 클래스를 `CreationEndpoint` 프로젝트의 CreationEndpointElement.cs 파일에 추가합니다. 이 클래스는 web.config 파일에 많은 `CreationEndpoint` 인스턴스를 저장하기 위해 구성에서 사용됩니다.  
  
    ```  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
    ```  
  
7.  솔루션을 빌드합니다.  
  
### <a name="host-the-workflow-in-iis"></a>IIS에서 워크플로 호스팅  
  
1.  IIS에서 `MyCreationEndpoint`라는 새 응용 프로그램을 만듭니다.  
  
2.  Workflow Designer에서 생성된 workflow1.xaml 파일을 응용 프로그램 디렉터리에 복사하고 workflow1.xamlx로 이름을 바꿉니다.  
  
3.  shared.dll 및 CreationEndpoint.dll 파일을 응용 프로그램의 bin 디렉터리에 복사합니다(bin 디렉터리가 없는 경우 만들어야 함).  
  
4.  `CreationEndpoint` 프로젝트에서 Web.config 파일의 내용을 다음 코드로 바꿉니다.  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.web>  
        <compilation debug="true" targetFramework="4.0" />  
      </system.web>   
    </configuration>  
    ```  
  
5.  `<system.web>` 요소 뒤에 다음 구성 코드를 추가하여 `CreationEndpoint`를 등록합니다.  
  
    ```xml  
    <system.serviceModel>  
        <!--register CreationEndpoint-->  
        <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
        <extensions>  
          <endpointExtensions>  
            <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, CreationEndpoint, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </endpointExtensions>  
        </extensions>  
    </system.serviceModel>  
    ```  
  
     이렇게 하면 `CreationEndpointCollection` 클래스가 등록되므로 web.config 파일에서 `CreationEndpoint`를 구성할 수 있습니다.  
  
6.  추가 `<service>` 요소 (후의 \</extensions > 태그)와 `CreationEndpoint` 들어오는 메시지를 수신 합니다.  
  
    ```xml  
    <services>  
          <!-- add endpoint to service-->  
          <service name="Workflow1" behaviorConfiguration="basicConfig" >  
            <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
          </service>  
        </services>  
    ```  
  
7.  추가 \<동작 > 요소 (후의  \< /서비스 > 태그) 서비스 메타 데이터를 사용 하도록 합니다.  
  
    ```xml  
    <behaviors>  
          <serviceBehaviors>  
            <behavior name="basicConfig">  
              <serviceMetadata httpGetEnabled="true" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
    ```  
  
8.  IIS 응용 프로그램 디렉터리에 web.config를 복사합니다.  
  
9. Internet Explorer를 시작 하 고 탐색 하 여 만들기 끝점이 작동 하는 경우 테스트 http://localhost/MyCreationEndpoint/Workflow1.xamlx합니다. Internet Explorer는 다음 화면을 표시해야 합니다.  
  
     ![서비스 테스트](../../../../docs/framework/wcf/feature-details/media/testservice.gif "TestService")  
  
### <a name="create-a-client-that-will-call-the-creationendpoint"></a>CreationEndpoint를 호출할 클라이언트 만들기  
  
1.  새 콘솔 응용 프로그램을 `CreationEndpointTest` 솔루션에 추가합니다.  
  
2.  System.ServiceModel.dll, System.ServiceModel.Activities 및 `Shared`에 대한 참조를 프로젝트에 추가합니다.  
  
3.  에 `Main` 메서드 만들기는 <xref:System.ServiceModel.ChannelFactory%601> 형식의 `IWorkflowCreation` 호출 <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>합니다. 이렇게 하면 프록시가 반환됩니다. 이 프록시에서 `Create`를 호출하여 IIS에서 호스트된 워크플로 인스턴스를 만들 수 있습니다.  
  
    ```  
    using System.Text;  
    using Shared;  
    using System.ServiceModel;  
  
    namespace CreationEndpointClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                try  
                {  
                    //client using BasicHttpBinding  
                    IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/CreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                    Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                    Console.WriteLine("Press return to exit ...");  
                    Console.ReadLine();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine(ex);  
                    Console.ReadLine();  
                }  
            }  
        }  
    }  
    ```  
  
4.  CreationEndpointClient를 실행합니다. 출력은 다음과 같습니다.  
  
    ```Output  
    Workflow Instance created using CreationEndpoint added in config. Instance Id: 0875dac0-2b8b-473e-b3cc-abcb235e9693Press return to exit ...  
    ```  
  
    > [!NOTE]
    >  워크플로가 콘솔 출력이 없는 IIS에서 실행되고 있기 때문에 워크플로의 출력은 표시되지 않습니다.  
  
## <a name="example"></a>예제  
 다음은 이 샘플의 전체 코드입니다.  
  
```xaml  
<!-— workflow1.xamlx -->  
<WorkflowService mc:Ignorable="sap"   
                 ConfigurationName="Workflow1"   
                 sap:VirtualizedContainerService.HintSize="263,230"   
                 Name="Workflow1"   
                 mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces"   
                 xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"   
                 xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
                 xmlns:mv="clr-namespace:Microsoft.VisualBasic;assembly=System"   
                 xmlns:mva="clr-namespace:Microsoft.VisualBasic.Activities;assembly=System.Activities"   
                 xmlns:p="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
                 xmlns:s="clr-namespace:System;assembly=mscorlib"   
                 xmlns:s1="clr-namespace:System;assembly=System"   
                 xmlns:s2="clr-namespace:System;assembly=System.Xml"   
                 xmlns:s3="clr-namespace:System;assembly=System.Core"   
                 xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities"   
                 xmlns:sap="http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation"   
                 xmlns:scg="clr-namespace:System.Collections.Generic;assembly=System"   
                 xmlns:scg1="clr-namespace:System.Collections.Generic;assembly=System.ServiceModel"   
                 xmlns:scg2="clr-namespace:System.Collections.Generic;assembly=System.Core"   
                 xmlns:scg3="clr-namespace:System.Collections.Generic;assembly=mscorlib"   
                 xmlns:sd="clr-namespace:System.Data;assembly=System.Data"   
                 xmlns:sl="clr-namespace:System.Linq;assembly=System.Core"   
                 xmlns:st="clr-namespace:System.Text;assembly=mscorlib"   
                 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <p:Sequence DisplayName="Sequential Service"   
              sad:XamlDebuggerXmlReader.FileName="c:\projects\CreationEndpointTest\CreationEndpoint\Service1.xamlx"   
              sap:VirtualizedContainerService.HintSize="233,200"   
              mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces">  
    <p:Sequence.Variables>  
      <p:Variable x:TypeArguments="CorrelationHandle" Name="handle" />  
      <p:Variable x:TypeArguments="x:Int32" Name="data" />  
    </p:Sequence.Variables>  
    <sap:WorkflowViewStateService.ViewState>  
      <scg3:Dictionary x:TypeArguments="x:String, x:Object">  
        <x:Boolean x:Key="IsExpanded">True</x:Boolean>  
      </scg3:Dictionary>  
    </sap:WorkflowViewStateService.ViewState>  
    <p:WriteLine sap:VirtualizedContainerService.HintSize="211,61" Text="Hello, world" />  
  </p:Sequence>  
</WorkflowService>  
```  
  
```csharp  
// CreationEndpointElement.cs  
using System;  
using System.Configuration;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Description;  
using Shared;  
  
namespace CreationEndpointTest  
{  
    //config element for CreationEndpoint  
    public class CreationEndpointElement : StandardEndpointElement  
    {  
        protected override Type EndpointType  
        {  
            get { return typeof(CreationEndpoint); }  
        }  
  
        protected override ConfigurationPropertyCollection Properties  
        {  
            get  
            {  
                ConfigurationPropertyCollection properties = base.Properties;  
                properties.Add(new ConfigurationProperty("name", typeof(String), null, ConfigurationPropertyOptions.IsRequired));  
                return properties;  
            }  
        }  
  
        protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
        {  
            return new CreationEndpoint();  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
    }  
  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
}  
```  
  
```xml  
<!-- web.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <!--register CreationEndpoint-->  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
    <extensions>  
      <endpointExtensions>  
        <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, Shared, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <!-- add endpoint to service-->  
      <service name="Workflow1" behaviorConfiguration="basicConfig" >  
        <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="basicConfig">  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```csharp  
// IWorkflowCreation.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
  
namespace Shared  
{  
    //service contract exposed from the endpoint  
    [ServiceContract(Name = "IWorkflowCreation")]  
    public interface IWorkflowCreation  
    {  
        [OperationContract(Name = "Create")]  
        Guid Create(IDictionary<string, object> inputs);  
  
        [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
        void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
    }  
}  
```  
  
```csharp  
// CreationEndpoint.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Channels;  
using System.ServiceModel;  
using System.Globalization;  
using System.Diagnostics;  
  
namespace Shared  
{  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
  
        public CreationEndpoint(Binding binding, EndpointAddress address)  
            : base(typeof(IWorkflowCreation), binding, address) { }  
  
        public CreationEndpoint()  
            : this(GetDefaultBinding(),  
                new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative)))) { }  
  
        static Uri DefaultBaseUri  
        {  
            get  
            {  
                if (defaultBaseUri == null)  
                {  
                    defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                        Process.GetCurrentProcess().Id,  
                        AppDomain.CurrentDomain.Id));  
                }  
                return defaultBaseUri;  
            }  
        }  
  
        //defaults to NetNamedPipeBinding  
        public static Binding GetDefaultBinding()  
        {  
            return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
        }  
  
        protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
        {  
            //Create was called by client  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                return Guid.Empty;  
            }  
  
            //CreateWithInstanceId was called by client  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                return (Guid)inputs[1];  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
        }  
  
        protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
        {  
            WorkflowCreationContext creationContext = new WorkflowCreationContext();  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to the workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
                //reply to client with instanceId  
                responseContext.SendResponse(instanceId, null);  
            }  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
            return creationContext;  
        }  
    }  
}  
```  
  
```csharp  
// CreationEndpointClient.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Shared;  
using System.ServiceModel;  
  
namespace CreationClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                //client using BasicHttpBinding  
                IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/MyCreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                Console.WriteLine("Press return to exit ...");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex);  
                Console.ReadLine();  
            }  
  
        }  
    }  
  
}  
```  
  
 `IWorkflowCreation`을 구현하는 서비스를 구현하지 않기 때문에 이 예제가 혼동스러울 수도 있습니다. 이는 `CreationEndpoint`가 이러한 구현 작업을 대신 수행하기 때문입니다.  
  
## <a name="see-also"></a>참고 항목  
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [인터넷 정보 서비스에서 호스팅](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [인터넷 정보 서비스 호스팅을 위한 최선의 방법](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [인터넷 정보 서비스 호스팅 지침](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)  
 [Windows 워크플로 아키텍처](../../../../docs/framework/windows-workflow-foundation/architecture.md)  
 [WorkflowHostingEndpoint 다시 시작 책갈피](../../../../docs/framework/windows-workflow-foundation/samples/workflowhostingendpoint-resume-bookmark.md)  
 [워크플로 디자이너 재호스트](../../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [Windows 워크플로 개요](../../../../docs/framework/windows-workflow-foundation/overview.md)
