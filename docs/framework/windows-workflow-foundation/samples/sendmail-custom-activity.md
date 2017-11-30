---
title: "SendMail 사용자 지정 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bffca162bfa7bf5a4d2b1bf23566f2b039391f4c
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="5c366-102">SendMail 사용자 지정 활동</span><span class="sxs-lookup"><span data-stu-id="5c366-102">SendMail Custom Activity</span></span>
<span data-ttu-id="5c366-103">이 샘플에서는 워크플로 응용 프로그램 내에서 사용하기 위해 <xref:System.Activities.AsyncCodeActivity>로부터 파생되는 사용자 지정 활동을 만들어 SMTP를 사용하여 메일을 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-103">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="5c366-104">사용자 지정 활동은 <xref:System.Net.Mail.SmtpClient>의 기능을 사용하여 전자 메일을 비동기적으로 보내고 인증된 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-104">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send e-mail asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="5c366-105">또한 테스트 모드, 토큰 바꾸기, 파일 템플릿 및 테스트 드롭 경로와 같은 몇 가지 최종 사용자 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-105">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="5c366-106">다음 표에서는 `SendMail` 활동의 인수에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-106">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="5c366-107">이름</span><span class="sxs-lookup"><span data-stu-id="5c366-107">Name</span></span>|<span data-ttu-id="5c366-108">형식</span><span class="sxs-lookup"><span data-stu-id="5c366-108">Type</span></span>|<span data-ttu-id="5c366-109">설명</span><span class="sxs-lookup"><span data-stu-id="5c366-109">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5c366-110">Host</span><span class="sxs-lookup"><span data-stu-id="5c366-110">Host</span></span>|<span data-ttu-id="5c366-111">문자열</span><span class="sxs-lookup"><span data-stu-id="5c366-111">String</span></span>|<span data-ttu-id="5c366-112">SMTP 서버 호스트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-112">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="5c366-113">포트</span><span class="sxs-lookup"><span data-stu-id="5c366-113">Port</span></span>|<span data-ttu-id="5c366-114">문자열</span><span class="sxs-lookup"><span data-stu-id="5c366-114">String</span></span>|<span data-ttu-id="5c366-115">호스트에 있는 SMTP 서비스의 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-115">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="5c366-116">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="5c366-116">EnableSsl</span></span>|<span data-ttu-id="5c366-117">bool</span><span class="sxs-lookup"><span data-stu-id="5c366-117">bool</span></span>|<span data-ttu-id="5c366-118"><xref:System.Net.Mail.SmtpClient>에서 SSL(Secure Sockets Layer)을 사용하여 연결을 암호화할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-118">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="5c366-119">UserName</span><span class="sxs-lookup"><span data-stu-id="5c366-119">UserName</span></span>|<span data-ttu-id="5c366-120">문자열</span><span class="sxs-lookup"><span data-stu-id="5c366-120">String</span></span>|<span data-ttu-id="5c366-121">보낸 사람의 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 속성을 인증하는 자격 증명을 설정할 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-121">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="5c366-122">암호</span><span class="sxs-lookup"><span data-stu-id="5c366-122">Password</span></span>|<span data-ttu-id="5c366-123">문자열</span><span class="sxs-lookup"><span data-stu-id="5c366-123">String</span></span>|<span data-ttu-id="5c366-124">보낸 사람의 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 속성을 인증하는 자격 증명을 설정할 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-124">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="5c366-125">Subject</span><span class="sxs-lookup"><span data-stu-id="5c366-125">Subject</span></span>|<span data-ttu-id="5c366-126"><xref:System.Activities.InArgument%601>\<문자열 ></span><span class="sxs-lookup"><span data-stu-id="5c366-126"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="5c366-127">메시지 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-127">Subject of the message.</span></span>|  
|<span data-ttu-id="5c366-128">Body</span><span class="sxs-lookup"><span data-stu-id="5c366-128">Body</span></span>|<span data-ttu-id="5c366-129"><xref:System.Activities.InArgument%601>\<문자열 ></span><span class="sxs-lookup"><span data-stu-id="5c366-129"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="5c366-130">메시지 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-130">Body of the message.</span></span>|  
|<span data-ttu-id="5c366-131">첨부 파일</span><span class="sxs-lookup"><span data-stu-id="5c366-131">Attachments</span></span>|<span data-ttu-id="5c366-132"><xref:System.Activities.InArgument%601>\<문자열 ></span><span class="sxs-lookup"><span data-stu-id="5c366-132"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="5c366-133">이 전자 메일 메시지에 첨부된 데이터를 저장하는 데 사용되는 첨부 파일 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-133">Attachment collection used to store data attached to this e-mail message.</span></span>|  
|<span data-ttu-id="5c366-134">전</span><span class="sxs-lookup"><span data-stu-id="5c366-134">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="5c366-135">이 전자 메일 메시지의 보낸 사람 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-135">From address for this e-mail message.</span></span>|  
|<span data-ttu-id="5c366-136">대상</span><span class="sxs-lookup"><span data-stu-id="5c366-136">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="5c366-137">이 전자 메일 메시지의 받는 사람이 들어 있는 주소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-137">Address collection that contains the recipients of this e-mail message.</span></span>|  
|<span data-ttu-id="5c366-138">CC</span><span class="sxs-lookup"><span data-stu-id="5c366-138">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="5c366-139">이 전자 메일 메시지의 CC(참조)를 받는 사람이 들어 있는 주소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-139">Address collection that contains the carbon copy (CC) recipients for this e-mail message.</span></span>|  
|<span data-ttu-id="5c366-140">BCC</span><span class="sxs-lookup"><span data-stu-id="5c366-140">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="5c366-141">이 전자 메일 메시지의 BCC(숨은 참조)를 받는 사람이 들어 있는 주소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-141">Address collection that contains the blind carbon copy (BCC) recipients for this e-mail message.</span></span>|  
|<span data-ttu-id="5c366-142">토큰</span><span class="sxs-lookup"><span data-stu-id="5c366-142">Tokens</span></span>|<span data-ttu-id="5c366-143"><xref:System.Activities.InArgument%601>< IDictionary\<문자열, 문자열 >></span><span class="sxs-lookup"><span data-stu-id="5c366-143"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="5c366-144">본문에서 바꿀 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-144">Tokens to replace in the body.</span></span> <span data-ttu-id="5c366-145">사용자는 이 기능을 통해 나중에 이 속성을 사용하여 제공된 토큰으로 바꿀 수 있는 일부 값을 본문에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-145">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="5c366-146">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="5c366-146">BodyTemplateFilePath</span></span>|<span data-ttu-id="5c366-147">문자열</span><span class="sxs-lookup"><span data-stu-id="5c366-147">String</span></span>|<span data-ttu-id="5c366-148">본문에 대한 템플릿의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-148">Path of a template for the body.</span></span> <span data-ttu-id="5c366-149">`SendMail` 활동은 이 파일의 내용을 본문 속성에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-149">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="5c366-150">템플릿에는 토큰 속성의 내용으로 바뀌는 토큰이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-150">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="5c366-151">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="5c366-151">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="5c366-152">이 속성이 설정되면 모든 전자 메일은 속성에 지정된 주소로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-152">When this property is set, all e-mails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="5c366-153">이 속성은 워크플로를 테스트할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-153">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="5c366-154">예를 들어 받는 사람에게 실제로 보내지는 않고 모든 전자 메일이 보내지는지 확인하려는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-154">For example, when you want to make sure that all e-mails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="5c366-155">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="5c366-155">TestDropPath</span></span>|<span data-ttu-id="5c366-156">문자열</span><span class="sxs-lookup"><span data-stu-id="5c366-156">String</span></span>|<span data-ttu-id="5c366-157">이 속성이 설정되면 모든 전자 메일은 지정된 파일에도 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-157">When this property is set, all e-mails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="5c366-158">이 속성은 보내는 전자 메일의 형식과 내용이 적합하지 확인하기 위해 워크플로를 테스트할 때나 디버그할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-158">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing e-mails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="5c366-159">솔루션 개념</span><span class="sxs-lookup"><span data-stu-id="5c366-159">Solution Contents</span></span>  
 <span data-ttu-id="5c366-160">솔루션에는 두 개의 프로젝트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-160">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="5c366-161">Project</span><span class="sxs-lookup"><span data-stu-id="5c366-161">Project</span></span>|<span data-ttu-id="5c366-162">설명</span><span class="sxs-lookup"><span data-stu-id="5c366-162">Description</span></span>|<span data-ttu-id="5c366-163">중요한 파일</span><span class="sxs-lookup"><span data-stu-id="5c366-163">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="5c366-164">SendMail</span><span class="sxs-lookup"><span data-stu-id="5c366-164">SendMail</span></span>|<span data-ttu-id="5c366-165">SendMail 활동</span><span class="sxs-lookup"><span data-stu-id="5c366-165">The SendMail activity</span></span>|<span data-ttu-id="5c366-166">1.  SendMail.cs: 기본 활동에 대한 구현</span><span class="sxs-lookup"><span data-stu-id="5c366-166">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="5c366-167">2.  SendMailDesigner.xaml 및 SendMailDesigner.xaml.cs: SendMail 활동에 대한 디자이너</span><span class="sxs-lookup"><span data-stu-id="5c366-167">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="5c366-168">3.  MailTemplateBody.htm: 보낼 전자 메일에 대한 템플릿</span><span class="sxs-lookup"><span data-stu-id="5c366-168">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="5c366-169">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="5c366-169">SendMailTestClient</span></span>|<span data-ttu-id="5c366-170">SendMail 활동을 테스트할 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-170">Client to test the SendMail activity.</span></span>  <span data-ttu-id="5c366-171">이 프로젝트에서는 SendMail 활동을 호출하는 두 가지 방식, 즉 선언 방식과 프로그래밍 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-171">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="5c366-172">1.  Sequence1.xaml: SendMail 활동을 호출하는 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-172">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="5c366-173">2.  Program.cs: Sequence1을 호출하고 SendMail을 사용하는 워크플로를 프로그래밍 방식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-173">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="5c366-174">SendMail 활동의 추가 구성</span><span class="sxs-lookup"><span data-stu-id="5c366-174">Further configuration of the SendMail activity</span></span>  
 <span data-ttu-id="5c366-175">샘플에는 표시되지 않지만 사용자는 SendMail 활동의 구성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-175">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="5c366-176">다음 세 개의 섹션에서는 이를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-176">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="5c366-177">본문에 지정된 토큰을 사용하여 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="5c366-177">Sending an email using tokens specified in the body</span></span>  
 <span data-ttu-id="5c366-178">이 코드 조각에서는 본문에 토큰이 포함된 전자 메일을 보낼 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-178">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="5c366-179">토큰이 본문 속성에 어떻게 제공되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-179">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="5c366-180">해당 토큰 값은 토큰 속성에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-180">Values for those tokens are provided to the tokens property.</span></span>  
  
```html  
IDictionary<string, string> tokens = new Dictionary<string, string>();  
tokens.Add("@name", "John Doe");  
tokens.Add("@date", DateTime.Now.ToString());  
tokens.Add("@server", "localhost");  
  
new SendMail  
{  
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Body = "Hello @name. This is a test email sent from @server. Current date is @date",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens)  
};  
```  
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="5c366-181">템플릿을 사용하여 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="5c366-181">Sending an email using a template</span></span>  
 <span data-ttu-id="5c366-182">이 조각에서는 본문의 템플릿 토큰을 사용하여 전자 메일을 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-182">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="5c366-183">`BodyTemplateFilePath` 속성을 설정할 때 Body 속성 값을 제공할 필요가 없습니다. 템플릿 파일의 내용이 본문에 복사되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-183">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
```  
new SendMail  
{    
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
    BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",   
};  
```  
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="5c366-184">테스트 모드에서 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="5c366-184">Sending Mails in Testing Mode</span></span>  
 <span data-ttu-id="5c366-185">이 코드 조각에서는 두 개의 테스트 속성을 설정 하는 방법을 보여 줍니다: 설정 하 여 `TestMailTo` 모든 메시지를 보낼에 john.doe@contoso.con (To, Cc, Bcc 값의 관계) 없이 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-185">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to john.doe@contoso.con (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="5c366-186">TestDropPath를 설정하면 나가는 모든 전자 메일이 제공된 경로에도 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-186">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="5c366-187">이러한 속성은 서로 관련되어 있지 않으므로 독립적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-187">These properties can be set independently (they are not related).</span></span>  
  
```  
new SendMail  
{    
   From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
   Subject = "Test email",  
   Host = "localhost",  
   Port = 25,  
   Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
   BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",  
   TestMailTo= new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   TestDropPath = @"c:\Samples\SendMail\TestDropPath\",  
};  
```  
  
## <a name="set-up-instructions"></a><span data-ttu-id="5c366-188">설치 지침</span><span class="sxs-lookup"><span data-stu-id="5c366-188">Set-Up Instructions</span></span>  
 <span data-ttu-id="5c366-189">이 샘플을 실행하려면 SMTP 서버에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-189">Access to a SMTP server is required for this sample.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5c366-190">다음 링크를 참조에 SMTP 서버를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-190"> setting up a SMTP server, see the following links.</span></span>  
  
-   [<span data-ttu-id="5c366-191">Microsoft Technet</span><span class="sxs-lookup"><span data-stu-id="5c366-191">Microsoft Technet</span></span>](http://go.microsoft.com/fwlink/?LinkId=166060)  
  
-   [<span data-ttu-id="5c366-192">SMTP 서비스 (IIS 6.0) 구성</span><span class="sxs-lookup"><span data-stu-id="5c366-192">Configuring the SMTP Service (IIS 6.0)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150456)  
  
-   [<span data-ttu-id="5c366-193">IIS 7.0: SMTP 전자 메일 구성</span><span class="sxs-lookup"><span data-stu-id="5c366-193">IIS 7.0: Configure SMTP E-Mail</span></span>](http://go.microsoft.com/fwlink/?LinkId=150457)  
  
-   [<span data-ttu-id="5c366-194">SMTP 서비스를 설치 하는 방법</span><span class="sxs-lookup"><span data-stu-id="5c366-194">How to Install the SMTP Service</span></span>](http://go.microsoft.com/fwlink/?LinkId=150458)  
  
 <span data-ttu-id="5c366-195">타사에서 제공하는 SMTP 에뮬레이터를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-195">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="5c366-196">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="5c366-196">To run this sample</span></span>  
  
1.  <span data-ttu-id="5c366-197">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 SendMail.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-197">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the SendMail.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5c366-198">올바른 SMTP 서버에 액세스할 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-198">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="5c366-199">설치 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c366-199">See the set-up instructions.</span></span>  
  
3.  <span data-ttu-id="5c366-200">서버 주소와 보낸 사람 및 받는 사람 전자 메일 주소를 사용하여 프로그램을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-200">Configure the program with your server address, and From and To e-mail addresses.</span></span>  
  
     <span data-ttu-id="5c366-201">이 샘플을 올바르게 실행하려면 Program.cs 및 Sequence.xaml에서 보낸 사람 및 받는 사람 주소와 SMTP 서버 주소를 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-201">To correctly run this sample, you may need to configure the value of From and To e-mail addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="5c366-202">프로그램은 메일을 두 가지 다른 방식으로 보내므로 두 위치에서 모두 주소를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-202">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4.  <span data-ttu-id="5c366-203">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-203">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5.  <span data-ttu-id="5c366-204">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-204">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5c366-205">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-205">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5c366-206">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5c366-206">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5c366-207">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="5c366-207">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5c366-208">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c366-208">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`