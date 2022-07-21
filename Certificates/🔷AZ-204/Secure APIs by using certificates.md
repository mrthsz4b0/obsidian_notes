

![[configure-request-certificates.png]]
## Check the thumbprint of a client certificate
`<choose>
    <when condition="@(context.Request.Certificate == null || context.Request.Certificate.Thumbprint != "desired-thumbprint")" >
        <return-response>
            <set-status code="403" reason="Invalid client certificate" />
        </return-response>
    </when>
</choose>`

### Check the thumbprint against certificates uploaded to API Management
1. obtain the certificates from your partners 
2. use the **Client certificates** page in the Azure portal to upload them to the API Management resource
3. add this code to your policy:
	`<choose>
	    <when condition="@(context.Request.Certificate == null || !context.Request.Certificate.Verify()  || !context.Deployment.Certificates.Any(c => c.Value.Thumbprint == context.Request.Certificate.Thumbprint))" >
	        <return-response>
	            <set-status code="403" reason="Invalid client certificate" />
	        </return-response>
	    </when>
	</choose>`
### Check the issuer and subject of a client certificate
`<choose>
	<when condition="@(context.Request.Certificate == null || context.Request.Certificate.Issuer != "trusted-issuer" || context.Request.Certificate.SubjectName.Name != "expected-subject-name")" >
		<return-response>
			<set-status code="403" reason="Invalid client certificate" />
		</return-response>
	</when>
</choose>`

**API URL suffix** must be unique for every API for a given publisher because API Management **distinguishes** APIs by their suffix.