# VerifiableID for Natural Person 
This document defines the data model of VerifiableID for Natural Persons, a W3C compliant Verifiable Credential.<br>
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
    <td>familyName</td>
    <td>
       Defines current family name(s) of the credential subject
       <br><br>
       Definition: <a href="http://mapping.semic.eu:81/vdm/about/html/http%3A%2F%2Fmapping.semic.eu%2Fvdm%2Fid%2Fcv%2F97146b7582f0b1ac5c31c80fd6b930c1">Current family name
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
    <td>firstName</td>
    <td>
      Defines current first name(s) of the credential subject
      <br><br> 
      Definition: <a href="http://mapping.semic.eu:81/vdm/about/html/http%3A%2F%2Fmapping.semic.eu%2Fvdm%2Fid%2Fcv%2F199e06484de8efa1617f6fb151a7db14">Current first name(s)</a> 
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
    <td>dateOfBirth</td>
    <td>
      Defines date of birth of the credential subject
      <br><br>
      Definition: <a href="http://mapping.semic.eu:81/vdm/about/html/http%3A%2F%2Fmapping.semic.eu%2Fvdm%2Fid%2Fcv%2F9c86f69e2870a160bdb9f834bdfd921f">Date of Birth</a> 
    </td>
    <td>date</td>
    <td>
      This property implements the eIDAS minimum data set. 
    </td>
    <td>
      Yes
    </td>
  </tr>

  <tr>
    <td>personalIdentifier</td>
    <td>
      Defines the unique national identifier of the credential subject (constructed by the sending Member State in accordance with the technical specifications for the purposes of cross-border identification and which is as persistent as possible in time)<br><br>
      Definition: <a href="http://mapping.semic.eu:81/vdm/about/html/http%3A%2F%2Fmapping.semic.eu%2Fvdm%2Fid%2Fcv%2F34c8fa875ac6bb9bc3eb15748292608f">Uniqueness identifier</a> 
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
    <td>nameAtBirth</td>
    <td>
      Defines the first name(s) of the credential subject at the time of their birth.
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
    <td>familyNameAtBirth</td>
    <td>
      Defines the first and the family name(s) of the credential subject at the time of their birth.
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
    <td>placeOfBirth</td>
    <td>
      Defines the place where the credential subject is born.
      <br><br>
      Definition: <a href="http://mapping.semic.eu:81/vdm/about/html/http%3A%2F%2Fmapping.semic.eu%2Fvdm%2Fid%2Fcv%2F5d353696b5653f80a6a1d54f1c04aac5">Place of birth</a> 
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
    <td>currentAddress</td>
    <td>
      Defines the current address of the credential subject. 
      <br><br>
      Definition: <a href="http://mapping.semic.eu:81/vdm/about/html/http%3A%2F%2Fmapping.semic.eu%2Fvdm%2Fid%2Fcv%2Fee4405abaf94e6bb7eb006230126ae89">Current address</a> 
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
    <td>gender</td>
    <td>
      Defines the gender of the credential subject.
      <br><br>
      Definition: <a href="http://mapping.semic.eu:81/vdm/about/html/http%3A%2F%2Fmapping.semic.eu%2Fvdm%2Fid%2Fcv%2F8c7e0e16e6c5716d42b4b49d2cff442f">Gender</a> 
    </td>
    <td>string</td>
    <td>
      This property implements the eIDAS minimum data set. 
    </td>
    <td>
      No 
    </td>
  </tr>