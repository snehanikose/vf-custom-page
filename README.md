# vf-custom-page
<apex:page standardController="Account" extensions="AccOpp" id="page">
  <table>
         <tr>
         
             <td>
             
                 <img src="/img/seasonLogos/Spring_18_bonsai_175x65.png"/>
             
             </td>
             
              <td>
             
                  <label>Opportunity Details for Account</label>
             
             </td>
         
         </tr>
     
     
     
     </table>
     <label><u>Account Details </u></label>
     <br/>
     <br/>
     <table>
        <tr>
            <td>
               <u> Account Name:</u> {!acc1.Name}
            </td>
            <td>
             </td>
            <td> 
             </td>
            <td>
            </td>
            <td>
               <u> Account Phone:</u> {!acc1.Phone}
            </td>
        </tr>
         <tr>
            <td>
              <u>  Annual Revenue:</u> {!acc1.AnnualRevenue}
            </td>
            <td>
             </td>
            <td> 
             </td>
            <td>
            </td>
            <td>
               <u> Account Number: </u>{!acc1.AccountNumber}
            </td>
        </tr>
         <tr>
            <td>
               <u> Billing Address: </u>{!acc1.BillingCity}
            </td>
            <td>
             </td>
            <td> 
             </td>
            <td>
            </td>
            <td>
               <u> Account Owner: </u>{!acc1.Owner.FirstName}
            </td>
        </tr>
        
    </table>
 <apex:form id="frm1">
     
     
     
<apex:pageblock id="pb"> 
    <apex:pageblocktable value="{!acc1}" var="a">
  
  <apex:column headerValue="Opportunity list">
   <apex:pageBlockTable value="{!acc1.Opportunities}" var="p">
      <apex:column value="{!p.name}"/>
      <apex:column value="{!p.Type}"/>
      <apex:column value="{!p.Amount}"/>
      <apex:column value="{!p.StageName}"/>
       <apex:column >          
           <apex:commandLink value="View"   onclick="window.location='/{!p.id}'; return false;"/>
               </apex:column>       
           <apex:column >
                <apex:actionRegion >
                <apex:commandLink immediate="true"  value="Delete" action="{!deleteOpp}" styleClass="delete" reRender="page,frm1,pb">
                  <apex:param name="rowId" value="{!p.Id}"/>
                 </apex:commandLink>
               </apex:actionRegion>
           </apex:column>
  </apex:pageBlockTable>
  </apex:column>
</apex:pageblocktable> 
    
</apex:pageblock>
 
</apex:form>
  
</apex:page>
                                        
