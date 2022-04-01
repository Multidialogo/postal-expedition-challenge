# Develop a web application with Aurelia framework 2

The application must be realized used the [https://aurelia.io/](Aurelia framework) ver.2, using the framework in the 
most idiomatic way.

The repository must contain a readme.md file that explains how to install and run the project.

## Delivery of the test

Test must be forked from this public repository, and then developed on own github account.

Send back the address of the page implementing the project to: selezione@multidialogo.it.

## Track: International shipping

### Country selection

The user selects the country from the [list of available countries](data/countries.json).

**Bonus**: the country selection interface uses the autocomplete

**Bonus**: try to include and use https://github.com/lipis/flag-icons, to draw country flags next to the country names

### Registered or unregistered mail

The user indicates if he want to use a registered or unregistered type of postage.

### Postage selection

The postage selection menu is populated after the country and registration type selection, excluding postages that are
not available for the select country and does not meet the registration requirement.

Any selectable postal options shows the price and the delivery time in days, inferred from the country, next to the 
postage name. (Prices are intended in Euro)

All the needed information are stored in the [postages configuration file](data/postages.json).

### Recipient data

Collect the recipient data.

A recipient must have the following information:

- type COMPANY|PERSON
- name and surname (if person) | company name (if company)
- address line 1 (mandatory)
- address line 2 (not mandatory)
- address line 3 (not mandatory)
- zip code
- country code (must be the one selected previous, must be read only field)

### Sender data

A sender must have the following information:

- type COMPANY|PERSON
- name and surname (if person) | company name (if company)
- address line 1 (mandatory)
- address line 2 (not mandatory)
- address line 3 (not mandatory)
- zip code
- country code

### Send the message

Collect sender data and recipient data in an object with two fields "sender" and "recipient", plus add the selected 
postage in the field "postage", including the "vector code" and the "postage code" and delivery information in a 
"delivery" section.

E.G.

```json
{
  "sender": {
    "type": "COMPANY",
    "name": "Acme Corp.",
    "addressLines": [
      "Fixture street, #42",
      "Donnington",
      "London"
    ],
    "zipCode": "019301",
    "countryCode": "uk"
  },
  "recipient": {
    "type": "PERSON",
    "name": "Mario",
    "surname": "Rossi",
    "addressLines": [
      "p.zza Sgaribaldi, n. 33",
      "San Benedetto del Tronto",
      "AP"
    ],
    "zipCode": "63074",
    "countryCode": "it"
  },
  "postage": {
    "vectorCode": "PT",
    "postageCode": "R1"
  },
  "delivery": {
    "days": 1,
    "price": 6.9
  }
}
```

Send the resulting json object as **body** by email to ignore.me@multidialogo.it, pressing submit form.

**Hint**: You can use a mailto link and uri encoding for the body parameter.



