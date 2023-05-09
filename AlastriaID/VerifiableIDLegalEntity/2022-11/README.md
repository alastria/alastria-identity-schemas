# VerifiableID for Legal Entity
This document defines the data model of VerifiableID for Legal Entities, a W3C compliant Verifiable Credential.<br>
<b>All EBSI descriptions modified to be AlastriaID compliant are striked out.</b><br><br>

Verifiable IDs are a special type of Verifiable Credentials (VCs) that Natural Persons and Legal Entities can put forward as evidence of who they are (comparable to a passport or a physical ID card). In other words, Verifiable IDs serve to enable identification and authentication and as such contain digital claims about certain personal attributes. If someone provides, for example, a Verifiable ID that states information about this person’s identity and is issued and signed by a government, service providers may trust and rely on this information (if they trust the government and the cryptography) to decide whether or not to conduct a transaction.

Verifiable ID is a Verifiable Attestation with the following top-level properties in the credentialSubject as defined in the table below.


## Credential subject

<table>
  <tr>
    <th>Property</th>
    <th>Description</th>
    <th>Type</th>
    <th>Notes</th>
    <th>Required</th>
  </tr>

  <tr>
    <td>id</td>
    <td>
       Defines the DID of the subject that is described by the Verifiable Attestation
       <br><br> 
       Definition: <a href="https://www.w3.org/TR/vc-data-model/#identifiers">https://www.w3.org/TR/vc-data-model/#identifiers</a> 
    </td>
    <td>string</td>
    <td>
      -
    </td>
    <td>
      Yes  
    </td>
  </tr>

  <tr>
    <td>legalPersonalIdentifier</td>
    <td>
       National/Legal Identifier of Credential Subject (constructed by the sending Member State in accordance with the technical specifications for the purposes of cross-border identification and which is as persistent as possible in time).
    </td>
    <td>string</td>
    <td>
      This property implements the eIDAS minimum data set. 
    </td>
    <td>
     No 
    </td>
  </tr>

  <tr>
    <td>legalName</td>
    <td>
     Official legal name of Credential Subject. 
    </td>
    <td>string</td>
    <td>
      This property implements the eIDAS minimum data set.
    </td>
    <td>
      Yes
    </td>
  </tr>

  <tr>
    <td>legalAddress</td>
    <td>
      Official legal address of Credential Subject. 
    </td>
    <td>date</td>
    <td>
      This property implements the eIDAS minimum data set. 
    </td>
    <td>
      No 
    </td>
  </tr>

  <tr>
    <td>VATRegistration</td>
    <td>
      VAT number of Credential Subject.
    </td>
    <td>string</td>
    <td>
      This property implements the eIDAS minimum data set. 
    </td>
    <td>
      No 
    </td>
  </tr>

  <tr>
    <td>taxReference</td>
    <td>
      Official tax reference number of Credential Subject.
    </td>
    <td>string</td>
    <td>
      This property implements the eIDAS minimum data set. 
    </td>
    <td>
      No
    </td>
  </tr>

  <tr>
    <td>LEI</td>
    <td>
      Official legal entity identifier (LEI) of Credential Subject (referred to in Commission Implementing Regulation (EU) No 1247/2012)
    </td>
    <td>string</td>
    <td>
      This property implements the eIDAS minimum data set. 
    </td>
    <td>
      No
    </td>
  </tr>

  <tr>
    <td>EORI</td>
    <td>
      Economic Operator Registration and Identification (EORI) of Credential Subject (referred to in Commission Implementing Regulation (EU) No 1352/2013)
    </td>
    <td>string</td>
    <td>
      This property implements the eIDAS minimum data set. 
    </td>
    <td>
      No
    </td>
  </tr>

  <tr>
    <td>SEED</td>
    <td>
     System for Exchange of Excise Data (SEED) of Credential Subject (i.e. excise number provided in Article 2(12) of Council Regulation (EC) No 389/2012
    </td>
    <td>string</td>
    <td>
      This property implements the eIDAS minimum data set. 
    </td>
    <td>
      No
    </td>
  </tr>

  <tr>
    <td>SIC</td>
    <td>
      Standard Industrial Classification (SIC) of Credential Subject (Article 3(1) of Directive 2009/101/EC of the European Parliament and of the Council.)
    </td>
    <td>string</td>
    <td>
      This property implements the eIDAS minimum data set. 
    </td>
    <td>
      No 
    </td>
  </tr>