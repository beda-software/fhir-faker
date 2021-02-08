# fhir-faker
A library for generating fake FHIR resources


## Usage example
```typescript
import fhirFaker from 'fhir-faker'


console.log(fhirFaker.dataTypes.fakeHumanName())
{ text: "Mr. Thomas Anderson", given: ["Thomas"], family: "Anderson", prefix: ["Mr."] }

console.log(fhirFaker.fakeHumanName({ family: "Simpson" }))
{ text: "Mr. Thomas Simpson", given: ["Thomas"], family: "Simpson", prefix: ["Mr."] }

console.log(fhirFaker.fakePatient())
[
  { 
    resourceType: "Patient", 
    id: "some-id",
    active: true,
    name: { text: "Mr. Thomas Simpson", given: ["Thomas"], family: "Simpson", prefix: ["Mr."] },
    managingOrganization: { resourceType: "Organization", id: "org-id", display: "Sacred Heart"}
  },
  {
    resourceType: "Organization", 
    id: "org-id",
    active: true,
    name: "Sacred Heart"
  }
]
```
