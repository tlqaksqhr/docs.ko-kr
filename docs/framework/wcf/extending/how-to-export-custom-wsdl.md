---
title: "방법: 사용자 지정 WSDL 내보내기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c1e4b58-b76b-472b-9635-2f80d42a0734
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4b34cc564dea5f189de29c9425c840ec96c80fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-export-custom-wsdl"></a>방법: 사용자 지정 WSDL 내보내기
이 항목에서는 사용자 지정 WSDL 정보를 내보내는 방법에 대해 설명합니다. 이 작업을 수행하려면 서비스에서 생성되는 WSDL에 사용자 지정 정보를 추가할 `WsdlDocumentationAttribute`라는 새 코드 특성을 정의합니다.  
  
### <a name="to-export-custom-wsdl-information"></a>사용자 지정 WSDL 정보를 내보내려면  
  
1.  <xref:System.ServiceModel.Description.IWsdlExportExtension> 인터페이스를 구현합니다. <xref:System.ServiceModel.Description.IOperationBehavior>, <xref:System.ServiceModel.Description.IContractBehavior> 또는 <xref:System.ServiceModel.Description.IEndpointBehavior> 인터페이스를 구현하는 클래스에서 이 인터페이스를 구현할 수 있습니다. <xref:System.ServiceModel.Channels.BindingElement>에서 파생된 클래스에서 이 인터페이스를 구현할 수도 있습니다. 이 샘플에서는 <xref:System.ServiceModel.Description.IWsdlExportExtension>를 구현하는 특성 클래스에서 <xref:System.ServiceModel.Description.IContractBehavior>을 구현합니다.  
  
2.  <xref:System.ServiceModel.Description.IWsdlExportExtension>은 <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> 및 <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>의 두 메서드를 정의합니다. 이러한 메서드를 사용하면 <xref:System.ServiceModel.Description.WsdlContractConversionContext>에 정보를 추가하거나 수정할 수 있습니다. <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> 메서드에서 이 샘플은 <xref:System.ServiceModel.Description.OperationDescription> 개체 컬렉션을 검색한 다음 컬렉션을 반복하여 `WsdlDocumentationAttribute`를 검사합니다. 특성이 있으면 특성에 연결된 텍스트가 추출되고, 요약 요소가 생성되고, 이 요약 요소가 작업의 `DocumentationElement`에 추가됩니다.  
  
    ```  
            public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
    {  
                Console.WriteLine("Inside ExportContract");  
    if (context.Contract != null)  
    {  
                    // Set the document element; if this is not done first, there is no XmlElement in the   
                    // DocumentElement property.  
                    context.WsdlPortType.Documentation = string.Empty;   
                    // Contract comments.  
                    XmlDocument owner = context.WsdlPortType.DocumentationElement.OwnerDocument;  
                    XmlElement summaryElement = Formatter.CreateSummaryElement(owner, this.Text);   
                    context.WsdlPortType.DocumentationElement.AppendChild(summaryElement);  
  
                    foreach (OperationDescription op in context.Contract.Operations)  
                    {  
                        Operation operation = context.GetOperation(op);  
                        object[] opAttrs = op.SyncMethod.GetCustomAttributes(typeof(WsdlDocumentationAttribute), false);  
                        if (opAttrs.Length == 1)  
                        {  
                            string opComment = ((WsdlDocumentationAttribute)opAttrs[0]).Text;  
  
                            // This.Text returns the string for the operation-level attributes.  
                            // Set the doc element; if this is not done first, there is no XmlElement in the   
                            // DocumentElement property.  
                            operation.Documentation = String.Empty;  
  
                            XmlDocument opOwner = operation.DocumentationElement.OwnerDocument;  
                            XmlElement newSummaryElement = Formatter.CreateSummaryElement(opOwner, opComment);  
                            operation.DocumentationElement.AppendChild(newSummaryElement);  
                        }  
                    }  
                }  
    ```  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 `WsdlDocumentationAttribute` 클래스의 전체 구현을 보여 줍니다.  
  
```  
public class WsdlDocumentationAttribute : Attribute, IContractBehavior, IWsdlExportExtension  
{  
string text;  
       XmlElement customWsdlDocElement = null;  
public WsdlDocumentationAttribute(string text)  
{ this.text = text;}  
  
       public WsdlDocumentationAttribute(XmlElement wsdlDocElement)  
        { this.customWsdlDocElement = wsdlDocElement; }  
  
        public XmlElement WsdlDocElement  
        {  
            get { return this.customWsdlDocElement; }  
            set { this.customWsdlDocElement = value; }  
        }  
       public string Text  
{  
get { return this.text; }  
set { this.text = value; }  
}  
  
     public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
{  
          Console.WriteLine("Inside ExportContract");  
if (context.Contract != null)  
{  
                // Set the document element; if this is not done first, there is no XmlElement in the   
                // DocumentElement property.  
                context.WsdlPortType.Documentation = string.Empty;   
                // Contract comments.  
                XmlDocument owner = context.WsdlPortType.DocumentationElement.OwnerDocument;  
                XmlElement summaryElement = Formatter.CreateSummaryElement(owner, this.Text);   
                context.WsdlPortType.DocumentationElement.AppendChild(summaryElement);  
  
                foreach (OperationDescription op in context.Contract.Operations)  
                {  
                    Operation operation = context.GetOperation(op);  
                    object[] opAttrs = op.SyncMethod.GetCustomAttributes(typeof(WsdlDocumentationAttribute), false);  
                    if (opAttrs.Length == 1)  
                    {  
                        string opComment = ((WsdlDocumentationAttribute)opAttrs[0]).Text;  
  
                        // This.Text returns the string for the operation-level attributes.  
                        // Set the document element; if this is not done first, there is no XmlElement in the   
                        // DocumentElement property.  
                        operation.Documentation = String.Empty;  
  
                        XmlDocument opOwner = operation.DocumentationElement.OwnerDocument;  
                        XmlElement newSummaryElement = Formatter.CreateSummaryElement(opOwner, opComment);  
                        operation.DocumentationElement.AppendChild(newSummaryElement);  
                    }  
                }  
            }  
        }  
  
public void ExportEndpoint(WsdlExporter exporter, WsdlEndpointConversionContext context)   
        {  
            Console.WriteLine("ExportEndpoint called.");  
        }  
  
        public void AddBindingParameters(ContractDescription description, ServiceEndpoint endpoint, BindingParameterCollection parameters)  
        { return; }  
  
        public void ApplyClientBehavior(ContractDescription description, ServiceEndpoint endpoint, ClientRuntime client)  
        { return; }  
  
        public void ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
        { return; }  
  
        public void Validate(ContractDescription description, ServiceEndpoint endpoint) { return; }  
    }  
  
  public class Formatter  
  {  
  
#region Utility Functions  
  
    public static XmlElement CreateSummaryElement(XmlDocument owningDoc, string text)  
    {  
      XmlElement summaryElement = owningDoc.CreateElement("summary");  
      summaryElement.InnerText = text;  
      return summaryElement;  
    }  
  
public static CodeCommentStatementCollection FormatComments(string text)  
{  
      /*  
       * Note that in Visual C# the XML comment format absorbs a   
       * documentation element with a line break in the middle. This sample  
       * could take an XmlElement and create code comments in which   
       * the element never had a line break in it.  
      */  
  
      CodeCommentStatementCollection collection = new CodeCommentStatementCollection();  
collection.Add(new CodeCommentStatement("From WsdlDocumentation:", true));  
collection.Add(new CodeCommentStatement(String.Empty, true));  
  
foreach (string line in WordWrap(text, 80))  
{  
collection.Add(new CodeCommentStatement(line, true));  
}  
  
collection.Add(new CodeCommentStatement(String.Empty, true));  
return collection;  
}  
  
public static Collection<string> WordWrap(string text, int columnWidth)  
{  
Collection<string> lines = new Collection<string>();  
System.Text.StringBuilder builder = new System.Text.StringBuilder();  
  
string[] words = text.Split(' ');  
foreach (string word in words)  
{  
if ((builder.Length > 0) && ((builder.Length + word.Length + 1) > columnWidth))  
{  
lines.Add(builder.ToString());  
builder = new System.Text.StringBuilder();  
}  
builder.Append(word);  
builder.Append(' ');  
}  
lines.Add(builder.ToString());  
  
return lines;  
}  
  
#endregion    
  
    public static XmlElement CreateReturnsElement(XmlDocument owner, string p)  
    {  
      XmlElement returnsElement = owner.CreateElement("returns");  
      returnsElement.InnerText = p;  
      return returnsElement;  
    }  
  }  
```  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터](../../../../docs/framework/wcf/feature-details/metadata.md)
