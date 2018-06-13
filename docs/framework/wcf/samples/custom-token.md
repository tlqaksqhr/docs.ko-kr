---
title: Custom Token
ms.date: 03/30/2017
ms.assetid: e7fd8b38-c370-454f-ba3e-19759019f03d
ms.openlocfilehash: c7219b94861cd23f27b331d1d3e5509654263430
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809851"
---
# <a name="custom-token"></a><span data-ttu-id="d416d-102">Custom Token</span><span class="sxs-lookup"><span data-stu-id="d416d-102">Custom Token</span></span>
<span data-ttu-id="d416d-103">이 샘플에는 Windows Communication Foundation (WCF) 응용 프로그램에 사용자 지정 토큰 구현을 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-103">This sample demonstrates how to add a custom token implementation into a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="d416d-104">이 예제에서는 클라이언트 신용 카드에 대한 정보를 서비스에 안전하게 전달하기 위해 `CreditCardToken`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-104">The example uses a `CreditCardToken` to securely pass information about client credit cards to the service.</span></span> <span data-ttu-id="d416d-105">이 토큰은 WS-Security 메시지 헤더로 전달되고 메시지 본문 및 다른 메시지 헤더와 함께 대칭 보안 바인딩 요소를 사용하여 서명 및 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-105">The token is passed in the WS-Security message header and is signed and encrypted using the symmetric security binding element along with message body and other message headers.</span></span> <span data-ttu-id="d416d-106">이 방법은 기본 제공 토큰이 충분하지 않은 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-106">This is useful in cases where the built-in tokens are not sufficient.</span></span> <span data-ttu-id="d416d-107">이 샘플에서는 기본 제공 토큰 중 하나를 사용하는 대신 사용자 지정 보안 토큰을 서비스에 제공하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-107">This sample demonstrates how to provide a custom security token to a service instead of using one of the built-in tokens.</span></span> <span data-ttu-id="d416d-108">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-108">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d416d-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d416d-110">즉, 이 샘플에서는 다음 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-110">To summarize, this sample demonstrates the following:</span></span>  
  
-   <span data-ttu-id="d416d-111">클라이언트가 사용자 지정 보안 토큰을 서비스에 전달하는 방법</span><span class="sxs-lookup"><span data-stu-id="d416d-111">How a client can pass a custom security token to a service.</span></span>  
  
-   <span data-ttu-id="d416d-112">서비스가 사용자 지정 보안 토큰을 사용하고 유효성을 검사하는 방법</span><span class="sxs-lookup"><span data-stu-id="d416d-112">How the service can consume and validate a custom security token.</span></span>  
  
-   <span data-ttu-id="d416d-113">어떻게 WCF 서비스 코드는 사용자 지정 보안 토큰을 포함 하 여 수신된 된 보안 토큰에 대 한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-113">How the WCF service code can obtain the information about received security tokens including the custom security token.</span></span>  
  
-   <span data-ttu-id="d416d-114">서버의 X.509 인증서를 사용하여 메시지 암호화 및 서명에 사용되는 대칭 키를 보호하는 방법</span><span class="sxs-lookup"><span data-stu-id="d416d-114">How the server's X.509 certificate is used to protect the symmetric key used for message encryption and signature.</span></span>  
  
## <a name="client-authentication-using-a-custom-security-token"></a><span data-ttu-id="d416d-115">사용자 지정 보안 토큰을 사용한 클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="d416d-115">Client Authentication Using a Custom Security Token</span></span>  
 <span data-ttu-id="d416d-116">서비스는 `BindingHelper` 및 `EchoServiceHost` 클래스를 사용하여 프로그래밍 방식으로 만들어진 단일 끝점을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-116">The service exposes a single endpoint that is programmatically created using `BindingHelper` and `EchoServiceHost` classes.</span></span> <span data-ttu-id="d416d-117">끝점은 하나의 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-117">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="d416d-118">바인딩은 `SymmetricSecurityBindingElement` 및 `HttpTransportBindingElement`를 사용하여 사용자 지정 바인딩으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-118">The binding is configured with a custom binding using `SymmetricSecurityBindingElement` and `HttpTransportBindingElement`.</span></span> <span data-ttu-id="d416d-119">이 샘플에서는 서비스의 X.509 인증서를 사용하여 전송 도중 대칭 키를 보호하고 WS-Security 메시지 헤더에서 사용자 지정 `SymmetricSecurityBindingElement`을 서명 및 암호화된 보안 토큰으로 전달하도록 `CreditCardToken`를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-119">This sample sets the `SymmetricSecurityBindingElement` to use a service's X.509 certificate to protect the symmetric key during transmission and to pass a custom `CreditCardToken` in a WS-Security message header as a signed and encrypted security token.</span></span> <span data-ttu-id="d416d-120">동작은 클라이언트 인증에 사용되는 서비스 자격 증명과 서비스 X.509 인증서에 대한 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-120">The behavior specifies the service credentials that are to be used for client authentication and also information about the service X.509 certificate.</span></span>  
  
```  
public static class BindingHelper  
{  
    public static Binding CreateCreditCardBinding()  
    {  
        HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();  
  
        // The message security binding element will be configured to require a credit card.  
        // The token that is encrypted with the service's certificate.   
        SymmetricSecurityBindingElement messageSecurity = new SymmetricSecurityBindingElement();  
        messageSecurity.EndpointSupportingTokenParameters.SignedEncrypted.Add(new CreditCardTokenParameters());  
        X509SecurityTokenParameters x509ProtectionParameters = new X509SecurityTokenParameters();  
        x509ProtectionParameters.InclusionMode = SecurityTokenInclusionMode.Never;  
        messageSecurity.ProtectionTokenParameters = x509ProtectionParameters;  
        return new CustomBinding(messageSecurity, httpTransport);  
    }  
}  
```  
  
 <span data-ttu-id="d416d-121">메시지에서 신용 카드 토큰을 사용하기 위해 샘플에서는 이 기능을 제공하는 사용자 지정 서비스 자격 증명을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-121">To consume a credit card token in the message, the sample uses custom service credentials to provide this functionality.</span></span> <span data-ttu-id="d416d-122">서비스 자격 증명 클래스는 `CreditCardServiceCredentials` 클래스에 있으며 `EchoServiceHost.InitializeRuntime` 메서드에서 서비스 호스트의 동작 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-122">The service credentials class is located in the `CreditCardServiceCredentials` class and is added to the behaviors collections of the service host in the `EchoServiceHost.InitializeRuntime` method.</span></span>  
  
```  
class EchoServiceHost : ServiceHost  
{  
    string creditCardFile;  
  
    public EchoServiceHost(parameters Uri[] addresses)  
        : base(typeof(EchoService), addresses)  
    {  
        creditCardFile = ConfigurationManager.AppSettings["creditCardFile"];  
        if (string.IsNullOrEmpty(creditCardFile))  
        {  
            throw new ConfigurationErrorsException("creditCardFile not specified in service config");  
        }  
  
        creditCardFile = String.Format("{0}\\{1}", System.Web.Hosting.HostingEnvironment.ApplicationPhysicalPath, creditCardFile);  
  
    }  
  
    override protected void InitializeRuntime()  
    {  
        // Create a credit card service credentials and add it to the behaviors.  
        CreditCardServiceCredentials serviceCredentials = new CreditCardServiceCredentials(this.creditCardFile);  
        serviceCredentials.ServiceCertificate.SetCertificate("CN=localhost", StoreLocation.LocalMachine, StoreName.My);  
        this.Description.Behaviors.Remove((typeof(ServiceCredentials)));  
        this.Description.Behaviors.Add(serviceCredentials);  
  
        // Register a credit card binding for the endpoint.  
        Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();  
        this.AddServiceEndpoint(typeof(IEchoService), creditCardBinding, string.Empty);  
  
        base.InitializeRuntime();  
    }  
}  
```  
  
 <span data-ttu-id="d416d-123">클라이언트 끝점은 서비스 끝점과 동일한 방식으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-123">The client endpoint is configured in a similar manner as the service endpoint.</span></span> <span data-ttu-id="d416d-124">클라이언트는 동일한 `BindingHelper` 클래스를 사용하여 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-124">The client uses the same `BindingHelper` class to create a binding.</span></span> <span data-ttu-id="d416d-125">설정의 나머지 부분은 `Client` 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-125">The rest of the setup is located in the `Client` class.</span></span> <span data-ttu-id="d416d-126">또한 클라이언트는 적절한 데이터와 함께 `CreditCardToken` 인스턴스를 클라이언트 끝점 동작 컬렉션에 추가하여 `CreditCardClientCredentials`에 포함될 정보와 설정 코드의 서비스 X.509 인증서에 대한 정보를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-126">The client also sets information to be contained in the `CreditCardToken` and information about the service X.509 certificate in the setup code by adding a `CreditCardClientCredentials` instance with the proper data to the client endpoint behaviors collection.</span></span> <span data-ttu-id="d416d-127">이 샘플에서는 `CN=localhost`로 설정된 주체 이름을 가진 X.509 인증서를 서비스 인증서로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-127">The sample uses X.509 certificate with subject name set to `CN=localhost` as the service certificate.</span></span>  
  
```  
Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();  
EndpointAddress serviceAddress = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
  
// Create a client with given client endpoint configuration  
channelFactory =   
new ChannelFactory<IEchoService>(creditCardBinding, serviceAddress);  
  
// configure the credit card credentials on the channel factory   
CreditCardClientCredentials credentials =   
      new CreditCardClientCredentials(  
      new CreditCardInfo(creditCardNumber, issuer, expirationTime));  
// configure the service certificate on the credentials  
credentials.ServiceCertificate.SetDefaultCertificate(  
      "CN=localhost", StoreLocation.LocalMachine, StoreName.My);  
  
// replace ClientCredentials with CreditCardClientCredentials  
channelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));  
channelFactory.Endpoint.Behaviors.Add(credentials);  
  
client = channelFactory.CreateChannel();  
  
Console.WriteLine("Echo service returned: {0}", client.Echo());  
  
((IChannel)client).Close();  
channelFactory.Close();  
```  
  
## <a name="custom-security-token-implementation"></a><span data-ttu-id="d416d-128">사용자 지정 보안 토큰 구현</span><span class="sxs-lookup"><span data-stu-id="d416d-128">Custom Security Token Implementation</span></span>  
 <span data-ttu-id="d416d-129">Wcf에서 사용자 지정 보안 토큰을 사용 하도록 설정 하려면 사용자 지정 보안 토큰의 개체 표현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-129">To enable a custom security token in WCF, create an object representation of the custom security token.</span></span> <span data-ttu-id="d416d-130">이 샘플에서는 `CreditCardToken` 클래스에 이 표현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-130">The sample has this representation in the `CreditCardToken` class.</span></span> <span data-ttu-id="d416d-131">개체 표현은 모든 관련 보안 토큰 정보를 보유하고 보안 토큰에 포함된 보안 키의 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-131">The object representation is responsible for holding all relevant security token information and to provide a list of security keys contained in the security token.</span></span> <span data-ttu-id="d416d-132">이 경우에는 신용 카드 보안 토큰에 보안 키가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-132">In this case, the credit card security token does not contain any security key.</span></span>  
  
 <span data-ttu-id="d416d-133">다음 섹션 네트워크를 통해 전송 하도록 사용자 지정 토큰을 사용 하도록 설정 하기 위해 수행 및 WCF 끝점에서 사용 해야 기능을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-133">The next section describes what must be done to enable a custom token to be transmitted over the wire and consumed by a WCF endpoint.</span></span>  
  
```  
class CreditCardToken : SecurityToken  
{  
    CreditCardInfo cardInfo;  
    DateTime effectiveTime = DateTime.UtcNow;  
    string id;  
    ReadOnlyCollection<SecurityKey> securityKeys;  
  
    public CreditCardToken(CreditCardInfo cardInfo) : this(cardInfo, Guid.NewGuid().ToString()) { }  
  
    public CreditCardToken(CreditCardInfo cardInfo, string id)  
    {  
        if (cardInfo == null)  
            throw new ArgumentNullException("cardInfo");  
  
        if (id == null)  
            throw new ArgumentNullException("id");  
  
        this.cardInfo = cardInfo;  
        this.id = id;  
  
        // The credit card token is not capable of any cryptography.  
        this.securityKeys = new ReadOnlyCollection<SecurityKey>(new List<SecurityKey>());  
    }  
  
    public CreditCardInfo CardInfo { get { return this.cardInfo; } }  
  
    public override ReadOnlyCollection<SecurityKey> SecurityKeys { get { return this.securityKeys; } }  
  
    public override DateTime ValidFrom { get { return this.effectiveTime; } }  
    public override DateTime ValidTo { get { return this.cardInfo.ExpirationDate; } }  
    public override string Id { get { return this.id; } }  
}  
```  
  
## <a name="getting-the-custom-credit-card-token-to-and-from-the-message"></a><span data-ttu-id="d416d-134">사용자 지정 신용 카드 토큰을 메시지로 가져가거나 메시지에서 가져오기</span><span class="sxs-lookup"><span data-stu-id="d416d-134">Getting the Custom Credit Card Token to and from the Message</span></span>  
 <span data-ttu-id="d416d-135">WCF의 보안 토큰 serializer는 메시지에 XML에서 보안 토큰의 개체 표현을 만들고 보안 토큰의 XML 양식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-135">Security token serializers in WCF are responsible for creating an object representation of security tokens from the XML in the message and creating a XML form of the security tokens.</span></span> <span data-ttu-id="d416d-136">또한 이러한 serializer는 보안 토큰을 가리키는 읽기 및 쓰기 키 식별자와 같은 다른 기능을 수행하지만 이 예제에서는 보안 토큰 관련 기능만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-136">They are also responsible for other functionality such as reading and writing key identifiers pointing to security tokens, but this example uses only security token-related functionality.</span></span> <span data-ttu-id="d416d-137">사용자 지정 토큰을 사용하도록 설정하려면 고유한 보안 토큰 serializer를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-137">To enable a custom token you must implement your own security token serializer.</span></span> <span data-ttu-id="d416d-138">이 샘플에서는 이를 위해 `CreditCardSecurityTokenSerializer` 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-138">This sample uses the `CreditCardSecurityTokenSerializer` class for this purpose.</span></span>  
  
 <span data-ttu-id="d416d-139">서비스에서 사용자 지정 serializer는 사용자 지정 토큰의 XML 양식을 읽고 이로부터 사용자 지정 토큰 개체 표현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-139">On the service, the custom serializer reads the XML form of the custom token and creates the custom token object representation from it.</span></span>  
  
 <span data-ttu-id="d416d-140">클라이언트에서 `CreditCardSecurityTokenSerializer` 클래스는 보안 토큰 개체 표현에 포함된 정보를 XML 작성기에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-140">On the client, the `CreditCardSecurityTokenSerializer` class writes the information contained in the security token object representation into the XML writer.</span></span>  
  
```  
public class CreditCardSecurityTokenSerializer : WSSecurityTokenSerializer  
{  
    public CreditCardSecurityTokenSerializer(SecurityTokenVersion version) : base() { }  
  
    protected override bool CanReadTokenCore(XmlReader reader)  
    {  
        XmlDictionaryReader localReader = XmlDictionaryReader.CreateDictionaryReader(reader);  
  
        if (reader == null) throw new ArgumentNullException("reader");  
  
        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))  
            return true;  
  
        return base.CanReadTokenCore(reader);  
    }  
  
    protected override SecurityToken ReadTokenCore(XmlReader reader, SecurityTokenResolver tokenResolver)  
    {  
        if (reader == null) throw new ArgumentNullException("reader");  
  
        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))  
        {  
            string id = reader.GetAttribute(Constants.Id, Constants.WsUtilityNamespace);  
  
            reader.ReadStartElement();  
  
            // Read the credit card number.  
            string creditCardNumber = reader.ReadElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace);  
  
            // Read the expiration date.  
            string expirationTimeString = reader.ReadElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace);  
            DateTime expirationTime = XmlConvert.ToDateTime(expirationTimeString, XmlDateTimeSerializationMode.Utc);  
  
            // Read the issuer of the credit card.  
            string creditCardIssuer = reader.ReadElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace);  
            reader.ReadEndElement();  
  
            CreditCardInfo cardInfo = new CreditCardInfo(creditCardNumber, creditCardIssuer, expirationTime);  
  
            return new CreditCardToken(cardInfo, id);  
        }  
        else  
        {  
            return WSSecurityTokenSerializer.DefaultInstance.ReadToken(reader, tokenResolver);  
        }  
    }  
  
    protected override bool CanWriteTokenCore(SecurityToken token)  
    {  
        if (token is CreditCardToken)  
            return true;  
  
        else  
            return base.CanWriteTokenCore(token);  
    }  
  
    protected override void WriteTokenCore(XmlWriter writer, SecurityToken token)  
    {  
        if (writer == null) { throw new ArgumentNullException("writer"); }  
        if (token == null) { throw new ArgumentNullException("token"); }  
  
        CreditCardToken c = token as CreditCardToken;  
        if (c != null)  
        {  
            writer.WriteStartElement(Constants.CreditCardTokenPrefix, Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace);  
            writer.WriteAttributeString(Constants.WsUtilityPrefix, Constants.Id, Constants.WsUtilityNamespace, token.Id);  
            writer.WriteElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardNumber);  
            writer.WriteElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace, XmlConvert.ToString(c.CardInfo.ExpirationDate, XmlDateTimeSerializationMode.Utc));  
            writer.WriteElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardIssuer);  
            writer.WriteEndElement();  
            writer.Flush();  
        }  
        else  
        {  
            base.WriteTokenCore(writer, token);  
        }  
    }  
}  
```  
  
## <a name="how-token-provider-and-token-authenticator-classes-are-created"></a><span data-ttu-id="d416d-141">토큰 공급자 및 토큰 인증자 클래스가 만들어지는 방법</span><span class="sxs-lookup"><span data-stu-id="d416d-141">How Token Provider and Token Authenticator Classes are Created</span></span>  
 <span data-ttu-id="d416d-142">클라이언트 및 서비스 자격 증명은 보안 토큰 관리자 인스턴스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-142">Client and service credentials are responsible for providing the security token manager instance.</span></span> <span data-ttu-id="d416d-143">보안 토큰 관리자 인스턴스는 토큰 공급자, 토큰 인증자 및 토큰 serializer를 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-143">The security token manager instance is used to get token providers, token authenticators and token serializers.</span></span>  
  
 <span data-ttu-id="d416d-144">토큰 공급자는 클라이언트 또는 서비스 자격 증명에 포함된 정보를 기반으로 토큰의 개체 표현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-144">The token provider creates an object representation of the token based on the information contained in the client or service credentials.</span></span> <span data-ttu-id="d416d-145">그런 다음 토큰 개체 표현은 앞 단원에 설명된 토큰 serializer를 사용하여 메시지에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-145">The token object representation is then written to the message using the token serializer (discussed in the previous section).</span></span>  
  
 <span data-ttu-id="d416d-146">토큰 인증자는 메시지에 도착하는 토큰의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-146">The token authenticator validates tokens that arrive in the message.</span></span> <span data-ttu-id="d416d-147">들어오는 토큰 개체 표현은 토큰 serializer에 의해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-147">The incoming token object representation is created by the token serializer.</span></span> <span data-ttu-id="d416d-148">그런 다음 이 개체 표현은 유효성 검사를 위해 토큰 인증자에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-148">This object representation is then passed to the token authenticator for validation.</span></span> <span data-ttu-id="d416d-149">토큰의 유효성이 검사되고 나면 토큰 인증자는 토큰에 포함된 정보를 나타내는 `IAuthorizationPolicy` 개체의 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-149">After the token is successfully validated, the token authenticator returns a collection of `IAuthorizationPolicy` objects that represent the information contained in the token.</span></span> <span data-ttu-id="d416d-150">이 정보는 권한 부여 결정을 수행하고 응용 프로그램에 대한 클레임을 제공하기 위해 나중에 메시지 처리 도중 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-150">This information is used later during the message processing to perform authorization decisions and to provide claims for the application.</span></span> <span data-ttu-id="d416d-151">이 예제에서 신용 카드 토큰 인증자는 이러한 목적을 위해 `CreditCardTokenAuthorizationPolicy`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-151">In this example, the credit card token authenticator uses `CreditCardTokenAuthorizationPolicy` for this purpose.</span></span>  
  
 <span data-ttu-id="d416d-152">토큰 serializer는 연결을 통해 토큰의 개체 표현을 가져오거나 가져갑니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-152">The token serializer is responsible for getting the object representation of the token to and from the wire.</span></span> <span data-ttu-id="d416d-153">이에 대해서는 위의 단원에서 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-153">This is discussed in the previous section.</span></span>  
  
 <span data-ttu-id="d416d-154">이 샘플에서는 클라이언트에서 서비스 방향으로만 신용 카드 토큰을 전송하므로 토큰 공급자는 클라이언트에서만 사용하고 토큰 인증자는 서비스에서만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-154">In this sample, we use a token provider only on the client and a token authenticator only on the service, because we want to transmit a credit card token only in the client-to-service direction.</span></span>  
  
 <span data-ttu-id="d416d-155">클라이언트의 기능은 `CreditCardClientCrendentials`, `CreditCardClientCredentialsSecurityTokenManager` 및 `CreditCardTokenProvider` 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-155">The functionality on the client is located in the `CreditCardClientCrendentials`, `CreditCardClientCredentialsSecurityTokenManager` and `CreditCardTokenProvider` classes.</span></span>  
  
 <span data-ttu-id="d416d-156">서비스에서 기능은 `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` 및 `CreditCardTokenAuthorizationPolicy` 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-156">On the service, the functionality resides in the `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` and `CreditCardTokenAuthorizationPolicy` classes.</span></span>  
  
```  
    public class CreditCardClientCredentials : ClientCredentials  
    {  
        CreditCardInfo creditCardInfo;  
  
        public CreditCardClientCredentials(CreditCardInfo creditCardInfo)  
            : base()  
        {  
            if (creditCardInfo == null)  
                throw new ArgumentNullException("creditCardInfo");  
  
            this.creditCardInfo = creditCardInfo;  
        }  
  
        public CreditCardInfo CreditCardInfo  
        {  
            get { return this.creditCardInfo; }  
        }  
  
        protected override ClientCredentials CloneCore()  
        {  
            return new CreditCardClientCredentials(this.creditCardInfo);  
        }  
  
        public override SecurityTokenManager CreateSecurityTokenManager()  
        {  
            return new CreditCardClientCredentialsSecurityTokenManager(this);  
        }  
    }  
  
public class CreditCardClientCredentialsSecurityTokenManager : ClientCredentialsSecurityTokenManager  
    {  
        CreditCardClientCredentials creditCardClientCredentials;  
  
        public CreditCardClientCredentialsSecurityTokenManager(CreditCardClientCredentials creditCardClientCredentials)  
            : base (creditCardClientCredentials)  
        {  
            this.creditCardClientCredentials = creditCardClientCredentials;  
        }  
  
        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)  
        {  
            // handle this token for Custom  
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)  
                return new CreditCardTokenProvider(this.creditCardClientCredentials.CreditCardInfo);  
            // return server cert  
            else if (tokenRequirement is InitiatorServiceModelSecurityTokenRequirement)  
            {  
                if (tokenRequirement.TokenType == SecurityTokenTypes.X509Certificate)  
                {  
                    return new X509SecurityTokenProvider(creditCardClientCredentials.ServiceCertificate.DefaultCertificate);  
                }  
            }  
  
            return base.CreateSecurityTokenProvider(tokenRequirement);  
        }  
  
        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)  
        {  
  
            return new CreditCardSecurityTokenSerializer(version);  
        }  
  
    }  
  
    class CreditCardTokenProvider : SecurityTokenProvider  
    {  
        CreditCardInfo creditCardInfo;  
  
        public CreditCardTokenProvider(CreditCardInfo creditCardInfo) : base()  
        {  
            if (creditCardInfo == null)  
            {  
                throw new ArgumentNullException("creditCardInfo");  
            }  
            this.creditCardInfo = creditCardInfo;  
        }  
  
        protected override SecurityToken GetTokenCore(TimeSpan timeout)  
        {  
            SecurityToken result = new CreditCardToken(this.creditCardInfo);  
            return result;  
        }  
    }  
  
public class CreditCardServiceCredentials : ServiceCredentials  
    {  
        string creditCardFile;  
  
        public CreditCardServiceCredentials(string creditCardFile)  
            : base()  
        {   
            if (creditCardFile == null)  
                throw new ArgumentNullException("creditCardFile");  
  
            this.creditCardFile = creditCardFile;  
        }  
  
        public string CreditCardDataFile  
        {  
            get { return this.creditCardFile; }  
        }  
  
        protected override ServiceCredentials CloneCore()  
        {  
            return new CreditCardServiceCredentials(this.creditCardFile);  
        }  
  
        public override SecurityTokenManager CreateSecurityTokenManager()  
        {  
            return new CreditCardServiceCredentialsSecurityTokenManager(this);  
        }  
    }  
  
public class CreditCardServiceCredentialsSecurityTokenManager : ServiceCredentialsSecurityTokenManager  
{  
        CreditCardServiceCredentials creditCardServiceCredentials;  
  
        public CreditCardServiceCredentialsSecurityTokenManager(CreditCardServiceCredentials creditCardServiceCredentials)  
            : base(creditCardServiceCredentials)  
        {  
            this.creditCardServiceCredentials = creditCardServiceCredentials;  
        }  
  
        public override SecurityTokenAuthenticator CreateSecurityTokenAuthenticator(SecurityTokenRequirement tokenRequirement, out SecurityTokenResolver outOfBandTokenResolver)  
        {  
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)  
            {  
                outOfBandTokenResolver = null;  
                return new CreditCardTokenAuthenticator(creditCardServiceCredentials.CreditCardDataFile);  
            }  
  
            return base.CreateSecurityTokenAuthenticator(tokenRequirement, out outOfBandTokenResolver);  
        }  
  
        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)  
        {  
            return new CreditCardSecurityTokenSerializer(version);  
        }  
    }  
  
    class CreditCardTokenAuthenticator : SecurityTokenAuthenticator  
    {  
        string creditCardsFile;  
        public CreditCardTokenAuthenticator(string creditCardsFile)  
        {  
            this.creditCardsFile = creditCardsFile;  
        }  
  
        protected override bool CanValidateTokenCore(SecurityToken token)  
        {  
            return (token is CreditCardToken);  
        }  
  
        protected override ReadOnlyCollection<IAuthorizationPolicy> ValidateTokenCore(SecurityToken token)  
        {  
            CreditCardToken creditCardToken = token as CreditCardToken;  
  
            if (creditCardToken.CardInfo.ExpirationDate < DateTime.UtcNow)  
                throw new SecurityTokenValidationException("The credit card has expired");  
            if (!IsCardNumberAndExpirationValid(creditCardToken.CardInfo))  
                throw new SecurityTokenValidationException("Unknown or invalid credit card");  
  
            // the credit card token has only 1 claim - the card number. The issuer for the claim is the  
            // credit card issuer  
  
            DefaultClaimSet cardIssuerClaimSet = new DefaultClaimSet(new Claim(ClaimTypes.Name, creditCardToken.CardInfo.CardIssuer, Rights.PossessProperty));  
            DefaultClaimSet cardClaimSet = new DefaultClaimSet(cardIssuerClaimSet, new Claim(Constants.CreditCardNumberClaim, creditCardToken.CardInfo.CardNumber, Rights.PossessProperty));  
            List<IAuthorizationPolicy> policies = new List<IAuthorizationPolicy>(1);  
            policies.Add(new CreditCardTokenAuthorizationPolicy(cardClaimSet));  
            return policies.AsReadOnly();  
        }  
  
        /// <summary>  
        /// Helper method to check if a given credit card entry is present in the User DB  
        /// </summary>  
        private bool IsCardNumberAndExpirationValid(CreditCardInfo cardInfo)  
        {  
            try  
            {  
                using (StreamReader myStreamReader = new StreamReader(this.creditCardsFile))  
                {  
                    string line = "";  
                    while ((line = myStreamReader.ReadLine()) != null)  
                    {  
                        string[] splitEntry = line.Split('#');  
                        if (splitEntry[0] == cardInfo.CardNumber)  
                        {  
                            string expirationDateString = splitEntry[1].Trim();  
                            DateTime expirationDateOnFile = DateTime.Parse(expirationDateString, System.Globalization.DateTimeFormatInfo.InvariantInfo, System.Globalization.DateTimeStyles.AdjustToUniversal);  
                            if (cardInfo.ExpirationDate == expirationDateOnFile)  
                            {  
                                string issuer = splitEntry[2];  
                                return issuer.Equals(cardInfo.CardIssuer, StringComparison.InvariantCultureIgnoreCase);  
                            }  
                            else  
                            {  
                                return false;  
                            }  
                        }  
                    }  
                    return false;  
                }  
            }  
            catch (Exception e)  
            {  
                throw new Exception("BookStoreService: Error while retrieving credit card information from User DB " + e.ToString());  
            }  
        }  
    }  
  
    public class CreditCardTokenAuthorizationPolicy : IAuthorizationPolicy  
    {  
        string id;  
        ClaimSet issuer;  
        IEnumerable<ClaimSet> issuedClaimSets;  
  
        public CreditCardTokenAuthorizationPolicy(ClaimSet issuedClaims)  
        {  
            if (issuedClaims == null)  
                throw new ArgumentNullException("issuedClaims");  
            this.issuer = issuedClaims.Issuer;  
            this.issuedClaimSets = new ClaimSet[] { issuedClaims };  
            this.id = Guid.NewGuid().ToString();  
        }  
  
        public ClaimSet Issuer { get { return this.issuer; } }  
  
        public string Id { get { return this.id; } }  
  
        public bool Evaluate(EvaluationContext context, ref object state)  
        {  
            foreach (ClaimSet issuance in this.issuedClaimSets)  
            {  
                context.AddClaimSet(this, issuance);  
            }  
  
            return true;  
        }  
    }  
```  
  
## <a name="displaying-the-callers-information"></a><span data-ttu-id="d416d-157">호출자의 정보 표시</span><span class="sxs-lookup"><span data-stu-id="d416d-157">Displaying the Callers' Information</span></span>  
 <span data-ttu-id="d416d-158">호출자의 정보를 표시하려면 다음 샘플 코드에서와 같이 `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-158">To display the caller's information, use the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` as shown in the following sample code.</span></span> <span data-ttu-id="d416d-159">`ServiceSecurityContext.Current.AuthorizationContext.ClaimSets`는 현재 호출자와 연관된 권한 부여 클레임을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-159">The `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contains authorization claims associated with the current caller.</span></span> <span data-ttu-id="d416d-160">이러한 클레임은 해당 `CreditCardToken` 컬렉션의 `AuthorizationPolicies` 클래스에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-160">The claims are supplied by the `CreditCardToken` class in its `AuthorizationPolicies` collection.</span></span>  
  
```  
bool TryGetStringClaimValue(ClaimSet claimSet, string claimType, out string claimValue)  
{  
    claimValue = null;  
    IEnumerable<Claim> matchingClaims = claimSet.FindClaims(claimType,  
        Rights.PossessProperty);  
    if (matchingClaims == null)  
        return false;  
    IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();  
    enumerator.MoveNext();  
    claimValue = (enumerator.Current.Resource == null) ? null :   
        enumerator.Current.Resource.ToString();  
    return true;  
}  
  
string GetCallerCreditCardNumber()  
{  
     foreach (ClaimSet claimSet in   
         ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)  
     {  
         string creditCardNumber = null;  
         if (TryGetStringClaimValue(claimSet,   
             Constants.CreditCardNumberClaim, out creditCardNumber))  
             {  
                 string issuer;  
                 if (!TryGetStringClaimValue(claimSet.Issuer,  
                        ClaimTypes.Name, out issuer))  
                 {  
                     issuer = "Unknown";  
                 }  
                 return String.Format(  
                   "Credit card '{0}' issued by '{1}'",   
                   creditCardNumber, issuer);  
        }  
    }  
    return "Credit card is not known";  
}  
```  
  
 <span data-ttu-id="d416d-161">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-161">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="d416d-162">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-162">Press ENTER in the client window to shut down the client.</span></span>  
  
## <a name="setup-batch-file"></a><span data-ttu-id="d416d-163">설치 배치 파일</span><span class="sxs-lookup"><span data-stu-id="d416d-163">Setup Batch File</span></span>  
 <span data-ttu-id="d416d-164">이 샘플에 포함된 Setup.bat 배치 파일을 사용하면 서버 인증서 기반 보안이 필요한 IIS에서 호스트되는 응용 프로그램을 실행하도록 관련 인증서가 있는 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-164">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run the IIS-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="d416d-165">다중 컴퓨터 구성이나 호스트되지 않는 환경에서 이 배치 파일을 사용하려면 배치 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-165">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>  
  
 <span data-ttu-id="d416d-166">아래에는 적절한 구성에서 실행할 수 있도록 배치 파일을 수정하는 데 도움이 되는 여러 관련 단원의 간략한 개요가 소개되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-166">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>  
  
-   <span data-ttu-id="d416d-167">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="d416d-167">Creating the server certificate:</span></span>  
  
     <span data-ttu-id="d416d-168">`Setup.bat` 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-168">The following lines from the `Setup.bat` batch file create the server certificate to be used.</span></span> <span data-ttu-id="d416d-169">`%SERVER_NAME%`변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-169">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="d416d-170">이 변수를 변경하여 고유의 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-170">Change this variable to specify your own server name.</span></span> <span data-ttu-id="d416d-171">이 배치 파일에서의 기본값은 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-171">The default in this batch file is localhost.</span></span> <span data-ttu-id="d416d-172">`%SERVER_NAME%` 변수를 변경할 경우 Client.cs 및 Service.cs 파일을 확인하여 localhost의 모든 인스턴스를 Setup.bat 스크립트에서 사용하는 서버 이름으로 대체해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-172">If you change the `%SERVER_NAME%` variable, you must go through the Client.cs and Service.cs files and replace all instances of localhost with the server name that you use in the Setup.bat script.</span></span>  
  
     <span data-ttu-id="d416d-173">인증서는 `LocalMachine` 저장 위치에 있는 My(개인) 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-173">The certificate is stored in My (Personal) store under the `LocalMachine` store location.</span></span> <span data-ttu-id="d416d-174">IIS에서 호스트되는 서비스의 경우 인증서는 LocalMachine 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-174">The certificate is stored in the LocalMachine store for the IIS-hosted services.</span></span> <span data-ttu-id="d416d-175">자체 호스팅 서비스의 경우 LocalMachine 문자열을 CurrentUser로 대체하여 CurrentUser 저장소 위치에 클라이언트 인증서를 저장하도록 배치 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-175">For self-hosted services, you should modify the batch file to store the client certificate in the CurrentUser store location by replacing the string LocalMachine with CurrentUser.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="d416d-176">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치:</span><span class="sxs-lookup"><span data-stu-id="d416d-176">Installing the server certificate into client's trusted certificate store:</span></span>  
  
     <span data-ttu-id="d416d-177">Setup.bat 배치 파일에서 다음 행은 클라이언트의 신뢰할 수 있는 사용자 저장소로 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-177">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="d416d-178">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-178">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="d416d-179">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-179">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    echo ************  
    echo copying server cert to client's TrustedPeople store  
    echo ************  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   <span data-ttu-id="d416d-180">IIS에서 호스트되는 서비스에서 인증서 개인 키에 액세스할 수 있게 하려면 IIS에서 호스트되는 프로세스가 실행 중인 사용자 계정에 개인 키에 대한 적절한 사용 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-180">To enable access to the certificate private key from the IIS-hosted service, the user account under which the IIS-hosted process is running must be granted appropriate permissions for the private key.</span></span> <span data-ttu-id="d416d-181">Setup.bat 스크립트에서 마지막 단계를 통해 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-181">This is accomplished by last steps in the Setup.bat script.</span></span>  
  
    ```  
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="d416d-182">Setup.bat 배치 파일은 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-182">The Setup.bat batch file is designed to be run from a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt.</span></span> <span data-ttu-id="d416d-183">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 설정된 PATH 환경 변수는 Setup.bat 스크립트에 필요한 실행 파일이 포함된 디렉터리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-183">The PATH environment variable set within the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="d416d-184">샘플을 설치하고 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="d416d-184">To set up and build the sample</span></span>  
  
1.  <span data-ttu-id="d416d-185">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d416d-186">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="d416d-187">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d416d-187">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="d416d-188">관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트 창을 열고 샘플 설치 폴더의 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-188">Open a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt window with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="d416d-189">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다. Makecert.exe가 있는 폴더가 경로에 포함되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-189">This installs all the certificates required for running the sample.Make sure that the path includes the folder where Makecert.exe is located.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d416d-190">샘플 사용을 마쳤으면 Cleanup.bat를 실행하여 인증서를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-190">Be sure to remove the certificates by running Cleanup.bat when finished with the sample.</span></span> <span data-ttu-id="d416d-191">다른 보안 샘플에도 동일한 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-191">Other security samples use the same certificates.</span></span>  
  
1.  <span data-ttu-id="d416d-192">client\bin 디렉터리에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-192">Launch Client.exe from client\bin directory.</span></span> <span data-ttu-id="d416d-193">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-193">Client activity is displayed on the client console application.</span></span>  
  
2.  <span data-ttu-id="d416d-194">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-194">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-run-the-sample-across-computer"></a><span data-ttu-id="d416d-195">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d416d-195">To run the sample across computer</span></span>  
  
1.  <span data-ttu-id="d416d-196">서비스 컴퓨터에 서비스 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-196">Create a directory on the service computer for the service binaries.</span></span>  
  
2.  <span data-ttu-id="d416d-197">서비스 프로그램 파일을 서비스 컴퓨터의 서비스 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-197">Copy the service program files into the service directory on the service computer.</span></span> <span data-ttu-id="d416d-198">CreditCardFile.txt를 복사해야 합니다. 그렇지 않으면 클라이언트에서 보내진 신용 카드 정보의 유효성을 신용 카드 인증자에서 검사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-198">Do not forget to copy CreditCardFile.txt; otherwise the credit card authenticator cannot validate credit card information sent from the client.</span></span> <span data-ttu-id="d416d-199">Setup.bat 및 Cleanup.bat 파일도 서비스 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-199">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="d416d-200">컴퓨터의 정규화된 도메인 이름을 포함하는 주체 이름을 가진 서버 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-200">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="d416d-201">`%SERVER_NAME%` 변수를 서비스가 호스트되는 컴퓨터의 정규화된 이름으로 변경할 경우 Setup.bat를 사용하여 이러한 서버 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-201">You can create one using the Setup.bat if you change the `%SERVER_NAME%` variable to fully-qualified name of the computer where the service is hosted.</span></span> <span data-ttu-id="d416d-202">관리자 권한으로 연 Visual Studio 명령 프롬프트에서 Setup.bat 파일을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-202">Note that the Setup.bat file must be run in a Visual Studio command prompt opened with administrator privileges.</span></span>  
  
4.  <span data-ttu-id="d416d-203">서버 인증서를 클라이언트의 CurrentUser-TrustedPeople 저장소에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-203">Copy the server certificate into the CurrentUser-TrustedPeople store on the client.</span></span> <span data-ttu-id="d416d-204">신뢰할 수 있는 발급자에 의해 서버 인증서가 발급되지 않은 경우에만 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-204">You must do this only if the server certificate is not issued by a trusted issuer.</span></span>  
  
5.  <span data-ttu-id="d416d-205">EchoServiceHost.cs 파일에서 인증서 주체 이름의 값을 변경하여 localhost 대신 정규화된 컴퓨터 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-205">In the EchoServiceHost.cs file, change the value of the certificate subject name to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6.  <span data-ttu-id="d416d-206">언어별 폴더의 \client\bin\ 폴더에서 클라이언트 프로그램 파일을 클라이언트 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-206">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
7.  <span data-ttu-id="d416d-207">Client.cs 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-207">In the Client.cs file, change the address value of the endpoint to match the new address of your service.</span></span>  
  
8.  <span data-ttu-id="d416d-208">Client.cs 파일에서 서비스 X.509 인증서의 주체 이름을 localhost 대신 원격 호스트의 정규화된 컴퓨터 이름과 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-208">In the Client.cs file change the subject name of the service X.509 certificate to match the fully-qualified computer name of the remote host instead of localhost.</span></span>  
  
9. <span data-ttu-id="d416d-209">클라이언트 컴퓨터의 명령 프롬프트 창에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-209">On the client computer, launch Client.exe from a command prompt window.</span></span>  
  
10. <span data-ttu-id="d416d-210">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-210">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="d416d-211">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="d416d-211">To clean up after the sample</span></span>  
  
1.  <span data-ttu-id="d416d-212">샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d416d-212">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d416d-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d416d-213">See Also</span></span>
