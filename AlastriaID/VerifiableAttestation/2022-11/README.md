# Verifiable Attestation
This document defines the data model of Verifiable Attestation, a W3C compliant Verifiable Credential.<br>
There are two types of Verifiable Attestation: Verifiable Attestation and Accredited Verifiable Attestation.<br>
<b>All EBSI descriptions modified to be AlastriaID compliant are striked out.</b><br><br>

<table>
  <tr>
    <th>Terminology</th>
    <th>Description</th>
    <th>Type</th>
    <th>Notes</th>
  </tr>

  <tr>
    <td>context</td>
    <td>
        Defines semantic context of the Verifiable Attestation.<br><br> Definition: <a href="https://www.w3.org/TR/vc-data-model/#contexts">https://www.w3.org/TR/vc-data-model/#contexts</a> 
    </td>
    <td>array&ltstring (URI)&gt</td>
    <td>
        JSON-LD contexts define terminology and identifiers for data to enable different systems, which exchange data, to “understand” each other by using the same terminology.<br><br>
        The content of this property must be an ordered set where the first item is a URI with the value: <a href="https://www.w3.org/2018/credentials/v1">"https://www.w3.org/2018/credentials/v1"</a> (“base context”).
    </td>
  </tr>

  <tr>
    <td>id</td>
    <td>
        Defines unique identifier of the Verifiable Attestation<br><br>
        Definition: <a href="https://www.w3.org/TR/vc-data-model/#identifiers">https://www.w3.org/TR/vc-data-model/#identifiers
    </td>
    <td>string(URI)</td>
    <td>
        Every Verifiable Attestation must have a unique identifier.<br><br>
        ID MUST be of the form: urn:uuid:&ltuuidv4&gt
    </td>
  </tr>

  <tr>
    <td>type</td>
    <td>
        Defines the Verifiable Credential type.<br><br> 
        Definition: <a href="https://www.w3.org/TR/vc-data-model/#types">https://www.w3.org/TR/vc-data-model/#types</a> 
    </td>
    <td>array&ltstring&gt</td>
    <td>
      Every Verifiable Credential must define its type.<br><br>
      The value of this property for a V-ID must be: 'VerifiableCredential', <s>'AccreditedVerifiableAttestation'</s>, 'VerifiableID'.
      <br><br>
      The types stated in the "type" field MUST go from more abstract to more concrete, being "VerifiableCredential" the first type for all credentials. This is not explicitly stated by EBSI but it's useful in order to know the concrete type for each credential.
    </td>
  </tr>

  <tr>
    <td>issuer</td>
    <td>
        Defines the issuer of the Verifiable Attestation.<br><br>
        Definition: <a href="https://www.w3.org/TR/vc-data-model/#issuer">https://www.w3.org/TR/vc-data-model/#issuer</a> 
    </td>
    <td>string(URI)</td>
    <td>
      <s>The value of this property must be an EBSI compliant DID.<br>
      The issuer DID must be registered in the Trusted Issuers Registry. </s> <br>
      The value of this property must be an AlastriaID compliant DID.<br>
      The issuer DID must be registered in the blockchain. 
    </td>
  </tr>

  <tr>
    <td>validFrom</td>
    <td>
        Defines the date and time, when the Verifiable Attestation becomes valid.
    </td>
    <td>dateTime</td>
    <td>
      The value of this property must be a combined date and time string.<br><br>
      The “validFrom” property will be added to the W3C VC data model to allow a distinction between the date a VC was issued (“issued”) and the date a VC becomes valid (“validFrom”). It is not yet included in the official W3C VC data model.<br><br>
      Format:  <a href="https://datatracker.ietf.org/doc/html/rfc3339">https://datatracker.ietf.org/doc/html/rfc3339</a>
    </td>
  </tr>

  <tr>
    <td>validUntil</td>
    <td>
      Defines the date and time, when the Verifiable Attestation expires (automatic invalidation). 
    </td>
    <td>dateTime</td>
    <td>
      The value of this property must be a combined date and time string.<br><br>
      The "validUntil" property will replace expirationDate in the future.<br><br>
      Format:  <a href="https://datatracker.ietf.org/doc/html/rfc3339">https://datatracker.ietf.org/doc/html/rfc3339</a>
    </td>
  </tr>

  <tr>
    <td>expirationDate</td>
    <td>
      Defines the date and time, when the Verifiable Attestation expires (automatic invalidation).
      Definition: <a href="https://www.w3.org/TR/vc-data-model/#expiration">https://datatracker.ietf.org/doc/html/rfc3339</a>  
    </td>
    <td>dateTime</td>
    <td>
      Date and time after which the credential should not be considered valid.<br><br>
      If present, the value of this property must be a combined date and time string.<br><br>
      Format: <a href="https://www.w3.org/TR/vc-data-model/#expiration">https://datatracker.ietf.org/doc/html/rfc3339</a>  
    </td>
  </tr>


  <tr>
    <td>credentialSubject</td>
    <td>
      Defines additional information about the subject that is described by the Verifiable Attestation<br><br>
      Definition: <a href="https://www.w3.org/TR/vc-data-model/#credential-subject">https://www.w3.org/TR/vc-data-model/#credential-subject</a><br>
    </td>
    <td>object</td>
    <td>
      The credential subject depends based on the type of Verifiable Attestation.
    </td>
  </tr>


  <tr>
    <td><s>credentialStatus</s></td>
    <td>
      Defines discovery information about the current status of a Verifiable Attestation.<br><br>
      Definition: <a href="https://www.w3.org/TR/vc-data-model/#status">https://www.w3.org/TR/vc-data-model/#status</a> 
    </td>
    <td>object</td>
    <td>
    </td>
  </tr>


  <tr>
    <td>credentialSchema</td>
    <td>
      Contains information about the credential schema (template) on which the Verifiable Attestation is based (via the Trusted Schemas Registry, TSR).<br>
      Definition: <a href="https://www.w3.org/TR/vc-data-model/#data-schemas">https://www.w3.org/TR/vc-data-model/#data-schemas</a> 
    </td>
    <td>object</td>
    <td>
    </td>
  </tr>


  <tr>
    <td>evidence</td>
    <td>
      Contains information about the process which resulted in the issuance of the Verifiable Attestation.<br><br>
      Definition: <a href="https://www.w3.org/TR/vc-data-model/#evidence">https://www.w3.org/TR/vc-data-model/#evidence</a> 
    </td>
    <td>array&ltobject&gt</td>
    <td>
      Evidence can contain one or more evidence objects.
    </td>
  </tr>

  <tr>
    <td>proof</td>
    <td>
      Contains information about the proof.<br><br>
      Definition: <a href="https://www.w3.org/TR/vc-data-model/#proofs-signatures">https://www.w3.org/TR/vc-data-model/#proofs-signatures</a> 
    </td>
    <td>object</td>
    <td>
      EBSI foresees the possibility to use different types of proofs for Verifiable Credentials, such as proofs derived from eIDAS keys (qualified) to DID keys (unqualified).  In EBSI 2.0, every Verifiable Attestation will only contain a single proof, which must be derived from eIDAS keys.<br><br>
      The proof property must only be present when Linked Data Signatures are used (which are currently unsupported)<br><br>
      For more information about proofs, check: E-signing and e-sealing Verifiable Credentials and Verifiable Presentations<br><br>
      This proof field is optional because the proof can be external instead of internal. 
    </td>
  </tr>


  <tr>
    <td><s>termsOfUse</s></td>
    <td>
      Defines the terms under which the Verifiable Attestation was issued.<br><br>
      Definition: <a href="https://www.w3.org/TR/vc-data-model/#terms-of-use">https://www.w3.org/TR/vc-data-model/#terms-of-use</a> 
    </td>
    <td>array&ltobject&gt</td>
    <td>
      <s>E.g., terms of use can contain information about the accreditation of the issuer of the Verifiable Attestation. Terms of use can contain one or more references to accreditations. </s> 
    </td>
  </tr>
</table>

<br></br>

## Credential subject
All credential subject objects MUST contain property id. Other properties are defined in data models of use cases.

<table>
  <tr>
    <th>Terminology</th>
    <th>Description</th>
    <th>Type</th>
    <th>Notes</th>
  </tr>

  <tr>
    <td>id</td>
    <td>
        Defines the DID of the subject that is described by the Verifiable Attestation.<br><br>
        Definition: <a href="https://www.w3.org/TR/vc-data-model/#identifier">https://www.w3.org/TR/vc-data-model/#identifier</a> 
    </td>
    <td>string</td>
    <td>
    </td>
  </tr>
</table>

<br></br>

## Credential status

<s><table>
  <tr>
    <th>Terminology</th>
    <th>Description</th>
    <th>Type</th>
    <th>Notes</th>
  </tr>

  <tr>
    <td>id</td>
    <td>
      References a record to enable verification of a Verifiable Attestation’s validity.
    </td>
    <td>string(URI)</td>
    <td>
    </td>
  </tr>

  <tr>
    <td>type</td>
    <td>
      Defines the Verifiable Attestation status type. 
    </td>
    <td>string</td>
    <td>
      E.g., CredentialStatusList2017
    </td>
  </tr>
</table></s>

<br></br>

## Credential schema 

<table>
  <tr>
    <th>Terminology</th>
    <th>Description</th>
    <th>Type</th>
    <th>Notes</th>
  </tr>

  <tr>
    <td>id</td>
    <td>
      <s>References the credential schema (template) stored on the (relevant) Trusted Schemas Registry (TSR) on which the Verifiable Attestation is based.</s>
      References the credential schema (template) stored on the alastria-identity-schemas repository. This can be stored in the blockchain in the future.
    </td>
    <td>string(URI)</td>
    <td>
    </td>
  </tr>

  <tr>
    <td>type</td>
    <td>
      Defines the credential schema type. 
    </td>
    <td>string</td>
    <td>
      MUST be FullJsonSchemaValidator2021 .
    </td>
  </tr>
</table>

<br></br>

## Evidence 
All evidence objects MUST contain properties id and type. Other properties are defined in data models of use cases, e.g., the presence of physical documents.

<table>
  <tr>
    <th>Terminology</th>
    <th>Description</th>
    <th>Type</th>
    <th>Notes</th>
  </tr>

  <tr>
    <td>id</td>
    <td>
      References a record of evidence. 
    </td>
    <td>string(URI)</td>
    <td>
    </td>
  </tr>

  <tr>
    <td>type</td>
    <td>
      Defines the evidence type. 
    </td>
    <td>string</td>
    <td>
    </td>
  </tr>
</table>

## Proof 

<s><table>
  <tr>
    <th>Terminology</th>
    <th>Description</th>
    <th>Type</th>
    <th>Notes</th>
  </tr>

  

  <tr>
    <td>type</td>
    <td>
      Defines the proof type.	 
    </td>
    <td>string</td>
    <td>
    </td>
  </tr>

<tr>
    <td>created</td>
    <td>
      Defines the date and time, when the proof has been created.	 
    </td>
    <td>dateTime</td>
    <td>
    </td>
  </tr>

<tr>
    <td>proofPurpose</td>
    <td>
      Defines the purpose of the proof.		 
    </td>
    <td>string</td>
    <td>
    </td>
  </tr>


<tr>
    <td>verificationMethod</td>
    <td>
      Contains information about the verification method/proof mechanisms..
    </td>
    <td>string(URI)</td>
    <td>
    </td>
  </tr>


<tr>
    <td>jws</td>
    <td>
      Defines the proof value in JWS signature format.	 
    </td>
    <td>string</td>
    <td>
    </td>
  </tr>
</table></s>

<br><br>

## Terms of use 
<s>Mandatory for Accredited Verifiable Attestations.<br>
<b>MUST be equal to VerifiableAccreditation.</b></s>

<s><table>
  <tr>
    <th>Terminology</th>
    <th>Description</th>
    <th>Type</th>
    <th>Notes</th>
  </tr>

  

  <tr>
    <td>id</td>
    <td>
      References a record of terms of use.	 
    </td>
    <td>string(URI)</td>
    <td>
      <s>If used for Verifiable Accreditation as in an Accredited Verifiable Attestation: References the Verifiable Accreditation stored as an attribute of the issuer in the Trusted Issuer Registry (TIR).</s> 
    </td>
  </tr>

<tr>
    <td>type</td>
    <td>
      Defines the term of use type.	 
    </td>
    <td>string</td>
    <td>
      <s>If used for Verifiable Accreditation as in an Accredited Verifiable Attestation: MUST be equal to a VerifiableAccreditation type.</s> 
    </td>
  </tr>
</table></s>

<br>

All the fields are required except validUntil, expirationDate, credentialStatus, evidence, proof and termsOfUse.<br>
credentialStatus and termsOfUse are required in an Accredited Verifiable Attestation.