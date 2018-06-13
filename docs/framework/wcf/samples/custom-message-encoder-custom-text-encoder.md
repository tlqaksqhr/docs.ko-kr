---
title: 'Custom Message Encoder: Custom Text Encoder'
ms.date: 03/30/2017
ms.assetid: 68ff5c74-3d33-4b44-bcae-e1d2f5dea0de
ms.openlocfilehash: 369706ecdc2e37a5fb62a448a273b045fe424df8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33808067"
---
# <a name="custom-message-encoder-custom-text-encoder"></a><span data-ttu-id="64836-102">Custom Message Encoder: Custom Text Encoder</span><span class="sxs-lookup"><span data-stu-id="64836-102">Custom Message Encoder: Custom Text Encoder</span></span>
<span data-ttu-id="64836-103">이 샘플에는 Windows Communication Foundation (WCF)를 사용 하 여 사용자 지정 텍스트 메시지 인코더를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64836-103">This sample demonstrates how to implement a custom text message encoder using Windows Communication Foundation (WCF).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="64836-104">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64836-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="64836-105">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="64836-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="64836-106">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="64836-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="64836-107">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64836-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Text`  
  
 <span data-ttu-id="64836-108"><xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> WCF의 u t F-8, utf-16 및 Big Endean 유니코드 인코딩만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-108">The <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> of WCF supports only the UTF-8, UTF-16 and Big Endean Unicode encodings.</span></span> <span data-ttu-id="64836-109">이 샘플의 사용자 지정 텍스트 메시지 인코더는 상호 운용성에 필요할 수 있는 모든 플랫폼에서 지원하는 문자 인코딩을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-109">The custom text message encoder in this sample supports all platform-supported character encoding that may be required for interoperability.</span></span> <span data-ttu-id="64836-110">이 샘플은 클라이언트 콘솔 프로그램(.exe), IIS(인터넷 정보 서비스)에서 호스팅하는 서비스 라이브러리(.dll) 및 텍스트 메시지 인코더 라이브러리(.dll)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="64836-110">The sample consists of a client console program (.exe), a service library (.dll) hosted by Internet Information Services (IIS) and a text message encoder library (.dll).</span></span> <span data-ttu-id="64836-111">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-111">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="64836-112">계약은 수학 연산(Add, Subtract, Multiply 및 Divide)을 노출시키는 `ICalculator` 인터페이스에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="64836-112">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="64836-113">클라이언트에서 지정된 수학 작업을 동기적으로 요청하면 서비스에서 결과로 회신합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-113">The client makes synchronous requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="64836-114">클라이언트와 서비스는 모두 기본 `CustomTextMessageEncoder` 대신 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-114">Both client and service uses the `CustomTextMessageEncoder` instead of the default <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span>  
  
 <span data-ttu-id="64836-115">사용자 지정 인코더 구현은 메시지 인코더 팩터리, 메시지 인코더, 메시지 인코딩 바인딩 요소 및 구성 처리기로 구성되며 다음 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64836-115">The custom encoder implementation consists of a message encoder factory, a message encoder, a message encoding binding element and a configuration handler, and demonstrates the following:</span></span>  
  
-   <span data-ttu-id="64836-116">사용자 지정 인코더 및 인코더 팩터리 빌드</span><span class="sxs-lookup"><span data-stu-id="64836-116">Building a custom encoder and encoder factory.</span></span>  
  
-   <span data-ttu-id="64836-117">사용자 지정 인코더의 바인딩 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="64836-117">Creating a binding element for a custom encoder.</span></span>  
  
-   <span data-ttu-id="64836-118">사용자 지정 바인딩 요소 통합에 사용자 지정 바인딩 구성 사용</span><span class="sxs-lookup"><span data-stu-id="64836-118">Using the custom binding configuration for integrating custom binding elements.</span></span>  
  
-   <span data-ttu-id="64836-119">사용자 지정 바인딩 요소의 파일 구성을 허용하는 사용자 지정 구성 처리기 개발</span><span class="sxs-lookup"><span data-stu-id="64836-119">Developing a custom configuration handler to allow file configuration of a custom binding element.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="64836-120">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="64836-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="64836-121">다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-121">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="64836-122">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-122">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="64836-123">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-123">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="64836-124">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-124">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="message-encoder-factory-and-the-message-encoder"></a><span data-ttu-id="64836-125">메시지 인코더 팩터리 및 메시지 인코더</span><span class="sxs-lookup"><span data-stu-id="64836-125">Message Encoder Factory and the Message Encoder</span></span>  
 <span data-ttu-id="64836-126"><xref:System.ServiceModel.ServiceHost> 또는 클라이언트 채널이 열려 있으면 디자인 타임 구성 요소 `CustomTextMessageBindingElement`는 `CustomTextMessageEncoderFactory`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64836-126">When the <xref:System.ServiceModel.ServiceHost> or the client channel is opened, the design time component `CustomTextMessageBindingElement` creates the `CustomTextMessageEncoderFactory`.</span></span> <span data-ttu-id="64836-127">이 팩터리는 `CustomTextMessageEncoder`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64836-127">The factory creates the `CustomTextMessageEncoder`.</span></span> <span data-ttu-id="64836-128">메시지 인코더는 스트리밍 모드와 버퍼링 모드에서 모두 작동하며</span><span class="sxs-lookup"><span data-stu-id="64836-128">The message encoder operates both in the streaming mode and the buffered mode.</span></span> <span data-ttu-id="64836-129"><xref:System.Xml.XmlReader> 및 <xref:System.Xml.XmlWriter>를 사용하여 각각 메시지를 읽고 씁니다.</span><span class="sxs-lookup"><span data-stu-id="64836-129">It uses the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> to read and write the messages respectively.</span></span> <span data-ttu-id="64836-130">최적화 된 XML 판독기 및 u t F-8, utf-16 및 Big Endean 유니코드를 지원 하는 WCF의 작성기 이러한 판독기와 작성기 모든 플랫폼에서 지 원하는 인코딩을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-130">As opposed to the optimized XML readers and writers of WCF that support only UTF-8, UTF-16 and Big-Endean Unicode these readers and writers support all platform supported encoding.</span></span>  
  
 <span data-ttu-id="64836-131">다음 코드 예제는 CustomTextMessageEncoder를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64836-131">The following code example shows the CustomTextMessageEncoder.</span></span>  
  
```csharp  
public class CustomTextMessageEncoder : MessageEncoder  
{  
    private CustomTextMessageEncoderFactory factory;  
    private XmlWriterSettings writerSettings;  
    private string contentType;  
  
    public CustomTextMessageEncoder(CustomTextMessageEncoderFactory factory)  
    {  
        this.factory = factory;  
  
        this.writerSettings = new XmlWriterSettings();  
        this.writerSettings.Encoding = Encoding.GetEncoding(factory.CharSet);  
        this.contentType = string.Format("{0}; charset={1}",   
            this.factory.MediaType, this.writerSettings.Encoding.HeaderName);  
    }  
  
    public override string ContentType  
    {  
        get  
        {  
            return this.contentType;  
        }  
    }  
  
    public override string MediaType  
    {  
        get   
        {  
            return factory.MediaType;  
        }  
    }  
  
    public override MessageVersion MessageVersion  
    {  
        get   
        {  
            return this.factory.MessageVersion;  
        }  
    }  
  
    public override Message ReadMessage(ArraySegment<byte> buffer, BufferManager bufferManager, string contentType)  
    {     
        byte[] msgContents = new byte[buffer.Count];  
        Array.Copy(buffer.Array, buffer.Offset, msgContents, 0, msgContents.Length);  
        bufferManager.ReturnBuffer(buffer.Array);  
  
        MemoryStream stream = new MemoryStream(msgContents);  
        return ReadMessage(stream, int.MaxValue);  
    }  
  
    public override Message ReadMessage(Stream stream, int maxSizeOfHeaders, string contentType)  
    {  
        XmlReader reader = XmlReader.Create(stream);  
        return Message.CreateMessage(reader, maxSizeOfHeaders, this.MessageVersion);  
    }  
  
    public override ArraySegment<byte> WriteMessage(Message message, int maxMessageSize, BufferManager bufferManager, int messageOffset)  
    {  
        MemoryStream stream = new MemoryStream();  
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);  
        message.WriteMessage(writer);  
        writer.Close();  
  
        byte[] messageBytes = stream.GetBuffer();  
        int messageLength = (int)stream.Position;  
        stream.Close();  
  
        int totalLength = messageLength + messageOffset;  
        byte[] totalBytes = bufferManager.TakeBuffer(totalLength);  
        Array.Copy(messageBytes, 0, totalBytes, messageOffset, messageLength);  
  
        ArraySegment<byte> byteArray = new ArraySegment<byte>(totalBytes, messageOffset, messageLength);  
        return byteArray;  
    }  
  
    public override void WriteMessage(Message message, Stream stream)  
    {  
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);  
        message.WriteMessage(writer);  
        writer.Close();  
    }  
}  
```  
  
 <span data-ttu-id="64836-132">다음 코드 예제는 메시지 인코더 팩터리를 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64836-132">The following code example shows how to build the message encoder factory.</span></span>  
  
```csharp  
public class CustomTextMessageEncoderFactory : MessageEncoderFactory  
{  
    private MessageEncoder encoder;  
    private MessageVersion version;  
    private string mediaType;  
    private string charSet;  
  
    internal CustomTextMessageEncoderFactory(string mediaType, string charSet,  
        MessageVersion version)  
    {  
        this.version = version;  
        this.mediaType = mediaType;  
        this.charSet = charSet;  
        this.encoder = new CustomTextMessageEncoder(this);  
    }  
  
    public override MessageEncoder Encoder  
    {  
        get   
        {   
            return this.encoder;  
        }  
    }  
  
    public override MessageVersion MessageVersion  
    {  
        get   
        {   
            return this.version;  
        }  
    }  
  
    internal string MediaType  
    {  
        get  
        {  
            return this.mediaType;  
        }  
    }  
  
    internal string CharSet  
    {  
        get  
        {  
            return this.charSet;  
        }  
    }  
}  
```  
  
## <a name="message-encoding-binding-element"></a><span data-ttu-id="64836-133">메시지 인코딩 바인딩 요소</span><span class="sxs-lookup"><span data-stu-id="64836-133">Message Encoding Binding Element</span></span>  
 <span data-ttu-id="64836-134">바인딩 요소에 WCF 런타임 스택 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-134">The binding elements allow the configuration of the WCF run-time stack.</span></span> <span data-ttu-id="64836-135">바인딩 요소는 필수 사용자 지정 메시지 인코더에서 WCF 응용 프로그램을 사용 하려면 런타임 스택의 적절 한 수준에서 적절 한 설정으로 메시지 인코더 팩터리를 만드는 합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-135">To use the custom message encoder in a WCF application, a binding element is required that creates the message encoder factory with the appropriate settings at the appropriate level in the run-time stack.</span></span>  
  
 <span data-ttu-id="64836-136">`CustomTextMessageBindingElement`는 <xref:System.ServiceModel.Channels.BindingElement> 기본 클래스에서 파생되며 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="64836-136">The `CustomTextMessageBindingElement` derives from the <xref:System.ServiceModel.Channels.BindingElement> base class and inherits from the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> class.</span></span> <span data-ttu-id="64836-137">따라서 다른 WCF 구성 요소가 메시지 인코딩 바인딩 요소가이 바인딩 요소 인식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64836-137">This allows other WCF components to recognize this binding element as being a message encoding binding element.</span></span> <span data-ttu-id="64836-138"><xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>의 구현은 일치하는 메시지 인코더 팩터리의 인스턴스를 알맞은 설정과 함께 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-138">The implementation of <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> returns an instance of the matching message encoder factory with appropriate settings.</span></span>  
  
 <span data-ttu-id="64836-139">`CustomTextMessageBindingElement`는 속성을 통해 `MessageVersion`, `ContentType` 및 `Encoding`에 대한 설정을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-139">The `CustomTextMessageBindingElement` exposes settings for `MessageVersion`, `ContentType`, and `Encoding` through properties.</span></span> <span data-ttu-id="64836-140">인코더는 Soap11Addressing 및 Soap12Addressing1 버전을 모두 지원하며</span><span class="sxs-lookup"><span data-stu-id="64836-140">The encoder supports both Soap11Addressing and Soap12Addressing1 versions.</span></span> <span data-ttu-id="64836-141">기본값은 Soap11Addressing1입니다.</span><span class="sxs-lookup"><span data-stu-id="64836-141">The default is Soap11Addressing1.</span></span> <span data-ttu-id="64836-142">`ContentType`의 기본값은 "text/xml"입니다.</span><span class="sxs-lookup"><span data-stu-id="64836-142">The default value of the `ContentType` is "text/xml".</span></span> <span data-ttu-id="64836-143">`Encoding` 속성을 사용하면 원하는 문자 인코딩의 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64836-143">The `Encoding` property allows you to set the value of the desired character encoding.</span></span> <span data-ttu-id="64836-144">샘플의 클라이언트 및 서비스가 사용 하 여 iso-8859-1 (Latin1) 문자 인코딩을에서 지원 되지 않습니다는 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> WCF의 합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-144">The sample client and service uses the ISO-8859-1 (Latin1) character encoding, which is not supported by the <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> of WCF.</span></span>  
  
 <span data-ttu-id="64836-145">다음 코드는 사용자 지정 텍스트 메시지 인코더를 사용하여 프로그래밍 방식으로 바인딩을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64836-145">The following code shows how to programmatically create the binding using the custom text message encoder.</span></span>  
  
```  
ICollection<BindingElement> bindingElements = new List<BindingElement>();  
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();  
CustomTextMessageBindingElement textBindingElement = new CustomTextMessageBindingElement();  
bindingElements.Add(textBindingElement);  
bindingElements.Add(httpBindingElement);  
CustomBinding binding = new CustomBinding(bindingElements);  
```  
  
## <a name="adding-metadata-support-to-the-message-encoding-binding-element"></a><span data-ttu-id="64836-146">메시지 인코딩 바인딩 요소에 메타데이터 지원 추가</span><span class="sxs-lookup"><span data-stu-id="64836-146">Adding Metadata Support to the Message Encoding Binding Element</span></span>  
 <span data-ttu-id="64836-147"><xref:System.ServiceModel.Channels.MessageEncodingBindingElement>에서 파생되는 모든 형식은 서비스에 대해 생성되는 WSDL 문서에서 SOAP 바인딩 버전을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-147">Any type that derives from <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> is responsible for updating the version of the SOAP binding in the WSDL document generated for the service.</span></span> <span data-ttu-id="64836-148">이 작업은 `ExportEndpoint` 인터페이스에서 <xref:System.ServiceModel.Description.IWsdlExportExtension> 메서드를 구현한 다음 생성된 WSDL을 수정하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="64836-148">This is done by implementing the `ExportEndpoint` method on the <xref:System.ServiceModel.Description.IWsdlExportExtension> interface and then modifying the generated WSDL.</span></span> <span data-ttu-id="64836-149">이 샘플에서 `CustomTextMessageBindingElement`는 `TextMessageEncodingBinidngElement`의 WSDL 내보내기 논리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-149">In this sample, the `CustomTextMessageBindingElement` uses the WSDL export logic from the `TextMessageEncodingBinidngElement`.</span></span>  
  
 <span data-ttu-id="64836-150">이 샘플에서 클라이언트 구성은 수동 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="64836-150">For this sample, the client configuration is hand configured.</span></span> <span data-ttu-id="64836-151">`CustomTextMessageBindingElement`는 그 동작을 설명하기 위해 정책 어설션을 내보내지 않으므로 Svcutil.exe를 사용하여 클라이언트 구성을 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64836-151">You cannot use Svcutil.exe to generate the client configuration because the `CustomTextMessageBindingElement` does not export a policy assertion to describe its behavior.</span></span> <span data-ttu-id="64836-152">일반적으로 사용자 지정 바인딩 요소에서 <xref:System.ServiceModel.Description.IPolicyExportExtension> 인터페이스를 구현하여 바인딩 요소에서 구현한 동작 또는 기능을 설명하는 사용자 지정 정책 어설션을 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-152">You should generally implement the <xref:System.ServiceModel.Description.IPolicyExportExtension> interface on a custom binding element to export a custom policy assertion that describes the behavior or capability implemented by the binding element.</span></span> <span data-ttu-id="64836-153">사용자 지정 바인딩 요소에 대 한 정책 어설션을 내보내야 하는 방법의 예제를 보려면는 [전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="64836-153">For an example of how to export a policy assertion for a custom binding element, see the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
## <a name="message-encoding-binding-configuration-handler"></a><span data-ttu-id="64836-154">메시지 인코딩 바인딩 구성 처리기</span><span class="sxs-lookup"><span data-stu-id="64836-154">Message Encoding Binding Configuration Handler</span></span>  
 <span data-ttu-id="64836-155">이전 단원에서는 프로그래밍 방식으로 사용자 지정 텍스트 메시지 인코더를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64836-155">The previous section shows how to use the custom text message encoder programmatically.</span></span> <span data-ttu-id="64836-156">`CustomTextMessageEncodingBindingSection`은 구성 파일 내에서 사용자 지정 텍스트 메시지 인코더를 사용하도록 지정할 수 있는 구성 처리기를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-156">The `CustomTextMessageEncodingBindingSection` implements a configuration handler that allows you to specify the use of a custom text message encoder within a configuration file.</span></span> <span data-ttu-id="64836-157">`CustomTextMessageEncodingBindingSection` 클래스는 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="64836-157">The `CustomTextMessageEncodingBindingSection` class derives from the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> class.</span></span> <span data-ttu-id="64836-158">`BindingElementType` 속성은 이 섹션에서 만들 바인딩 요소의 형식을 구성 시스템에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="64836-158">The `BindingElementType` property informs the configuration system of the type of binding element to create for this section.</span></span>  
  
 <span data-ttu-id="64836-159">`CustomTextMessageBindingElement`에 정의된 모든 설정은 `CustomTextMessageEncodingBindingSection`에 속성으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="64836-159">All of the settings defined by `CustomTextMessageBindingElement` are exposed as the properties in the `CustomTextMessageEncodingBindingSection`.</span></span> <span data-ttu-id="64836-160"><xref:System.Configuration.ConfigurationPropertyAttribute>는 구성 요소 특성을 속성에 매핑하고 특성이 설정되지 않은 경우 기본값을 설정하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-160">The <xref:System.Configuration.ConfigurationPropertyAttribute> assists in mapping the configuration element attributes to the properties and setting default values if the attribute is not set.</span></span> <span data-ttu-id="64836-161">구성의 값이 로드되어 형식의 속성에 적용된 후에는 속성을 바인딩 요소의 구체적인 인스턴스로 변환하는 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A> 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="64836-161">After the values from configuration are loaded and applied to the properties of the type, the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A> method is called, which converts the properties into a concrete instance of a binding element.</span></span>  
  
 <span data-ttu-id="64836-162">이 구성 처리기는 서비스나 클라이언트의 App.config 또는 Web.config에 있는 다음 표현에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="64836-162">This configuration handler maps to the following representation in the App.config or Web.config for the service or client.</span></span>  
  
```xml  
<customTextMessageEncoding encoding="utf-8" contentType="text/xml" messageVersion="Soap11Addressing1" />  
```  
  
 <span data-ttu-id="64836-163">이 샘플은 ISO-8859-1 인코딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-163">The sample uses the ISO-8859-1 encoding.</span></span>  
  
 <span data-ttu-id="64836-164">이 구성 처리기를 사용하려면 다음 구성 요소를 사용하여 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64836-164">To use this configuration handler it must be registered using the following configuration element.</span></span>  
  
```xml  
<extensions>  
    <bindingElementExtensions>  
        <add name="customTextMessageEncoding" type="   
Microsoft.ServiceModel.Samples.CustomTextMessageEncodingBindingSection,   
                  CustomTextMessageEncoder" />  
    </bindingElementExtensions>  
</extensions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="64836-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64836-165">See Also</span></span>
