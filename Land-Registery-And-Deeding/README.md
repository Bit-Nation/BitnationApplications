Land-Registery-And-Deeding
==========================

A Stake in the Ground.



#Overview


BITNATION is an experimental form of Do-It-Yourself governance using decentralized, trustless models such as Bitcoin’s blockchain. Its key principle is that all participation is  voluntary. Meaning that there’s a community consent, and approval, timestamped in the blockchain for later reference, for every claim, and transaction.
Objective


Design BITNATION’s initial land registry and deed protocol that will be applicable for places where currently there are no functioning land registry and deeding services. Those could, for instance, be the Favelas in Brazil, or the suburbs in Ghana. It will help many countries to foster peace in their communities through resolving land disputes in a peaceful manner, and unlock wealth through securing properties. A deeded property enable people to lend money against collateral to start companies or get education, and encourages investments in the property itself.


In addition to securing their land on the blockchain, they can also refer to the LandID on other contracts, like marriage, wills, death certificates, birth certificates etc.


This is an experiment, and we would like as much community input as possible. We’re trying to use low-tech code and equipment in order to scale this in areas with scarce economic and technological resources, and knowledge. Any and all input is appreciated.


#Process for BITNATION Land Registry and Deed Pilot


The process contains three essential strands: land survey, land registry, and land deeding. However, before beginning it’s also key to understand the local context.

#1. Decide on a place

We have chosen Ghana as the place for the first pilot, because Ghana need improved land rights to bolster their autonomy and economy. We also chose Ghana because of the Dream Bitcoin Foundation in Ghana and their enthusiasm to work on this project with us. 

#2. Background research and assessment

What is the specific context -- how is the land used, what sort of contract exist, how can it be improved upon?

Resource rights and management:

*Water Rights

*Shared Wells

*Shared Sewage

*Mining Rights

*Community land: Parks, Streets, etc

*Shared Cattle

*Other shared resources

Ghana land registery and deed open source reading material:

1. http://www.fig.net/pub/fig2006/papers/ps07/ps07_15_sittie_0848.pdf
2. http://www.doingbusiness.org/data/exploreeconomies/ghana/registering-property
3. http://usaidlandtenure.net/sites/default/files/country-profiles/full-reports/USAID_Land_Tenure_Ghana_Profile_0.pdf
4. http://ghanahouseplans.com/gh/how-to-register-your-land-in-ghana.html
5. https://www.fig.net/pub/accra/ppt/ts06/ts06_02_fosu_derby_ppt.pdf
6. http://www.fig.net/pub/accra/papers/ts14/ts14_03_kuntumensah.pdf
#3. Speak with the community leaders, and others

Arrange meetings with community leaders in areas suitable for tests: areas where people live in (have property) and are currently non-deeded. Speak with the community leaders to see understand their perception on the land situation, and if they’re interested in trying out the registry pilot. 
Collect information on how land contracts are managed currently, and what people like/ dislike with the system. Conduct research with open-ended questions amongst different parts of the community. 
Research local water rights, mining rights. Map out shared community resources in the pilot area: shared wells, shared sewage, shared electricity lines, etc.

#4. Come to agreement

Agree on where, when to do the pilot and who should be involved.

#5. Community workshop

A workshop with people in the area to explain the benefits of land registry and deeding, how the blockchain works in its function of a distributed public ledger, and helping people through the process of setting up their own PGP keys.

The workshop will need to be carefully prepared in advance.

#6. Decide on test area

It could be a small street or a few houses with land bordering each other, perhaps 4-5 pieces of land owned by different persons. The strategy is that people with bordering land sign off on a common map with their public keys, so that it’s verifiable that the community agreed on the boundaries, not just individual owners.

#7. Setup Survey Markers

Leave the survey markers with the community (around 30 of them, assuming there are 4-5 plots of lands to survey, and further assuming they’re not all perfectly rectangular), and spend the time it takes to agree on where the markers are set-up, defining the boundaries between the lands. 

* Survey markers should be of durable materials to keep as landmarks over time. 
This video can be used as inspiration: https://www.youtube.com/watch?v=fIetDYnj9Z0

* Survey markers might carry a unique ID (number, sticker, RF-ID). 

Survey grade GPS equipment is expected to become increasingly cheap and accurate over the next few years ahead. The need for durable markers in the ground will therefore be of lesser importance in the future. This implies that the application of survey markers should rather be optional than mandatory.

#8. Survey GPS/ GNSS hardware

The survey equipment should perform at least as accurate as government requirement in the local region.
For the initial demo project, equipment will be rented locally. 

On the longer term we aim to facilitate easy access to cheap survey hardware in the form of a smartphone accessory.

The make and model of equipment used as well as accuracy assessment data should be recorded for each survey point. The urban canyons may influence the accuracy, for instance if the survey marker is in between tall trees or buildings. Hence, when conducting the pilot we will try to find an area with mainly low buildings. 

This technology is improving rapidly with new PPP global augmentation services and low cost RTK products are being released frequently, from various vendors.

Another approach to mapping could be accurately georectified aerial images. Here are two relatively cheap and simple means that enables high resolution aerial photography.

Balloon Camera http://store.publiclab.org/products/balloon-mapping-kit

Drone on a leash http://www.fotokite.com/#product

It could be an practical approach to have RTK GNSS receiver with build in camera and WiFi / Bluetooth connectivity, that could be carried on a simple cheap quadcopter on a lesh or a balloon.

A micro drone with a camera could also be an option

http://www.micro-drone.co.uk

http://www.bitcraze.se/2012/10/another-key-chain-camera-hack

The pro and cons in terms of cost, availability, productivity, useability, image quality, reliability and so on for the various options should be investigated.


#9. Enter GPS Data 

Evaluate available OpenStreetMap editors for creating polygon plots. 
Enter the GPS coordinates of polygons in the Open Street Map cadastral layer. 
Other platforms to consider instead of OpenStreetMap includes GeoCommons, QGIS and GeoServer. 
Refer nodes to the unique ID’s on each survey marker. 

Gather the community together to give consensus on the map, both of their own land, and the neighbouring lands. If there need to be time to make sure consensus is met, that should be taken into account.

#10. Give survey markers individual IDs

#11. Get the owners of the x amount of land to sign of the map with their public keys

#12. Register Individual Deed Contracts

#13. Contracts for Rentals, Sale, Occupation, etc


#Protocol

In order to keep this simple, we can start with the basic functions of a land registry: register a region, split a region and merge regions. 

BN_LAND_REGISTER

FIELD
DESCRIPTION
Jurisdiction/Name
Country/State/City/Community
Proof of rights
HASH of documents proving land rights
Geometry
List of geospatial coordinates, resulting in a non-self intersecting polygon.
Owner
Public key for community
Signatures
Community members x 4 or 5

Message validation

Name/Jurisdiction should be unique? (Perhaps Name/Jurisdiction should be one field)
No land overlap will be allowed, if the registration polygon intersects any of the already existing registered regions it will be considered invalid
Geometry should be a non-self intersecting polygon

New owner’s public key is multi-signature and is governed by the community itself,  the BITNATION does not involve itself with how they will split the property amongst community members.

BN_LAND_SPLIT

FIELD
DESCRIPTION
INPUT
ID of region
(hash of C_LAND_REGISTER message)

Payments:
A: ??? BTC
B: ??? BTC
OUTPUTS
List of new owners and regions defined by list of geospatial coordinates for each.

OWNER A: (A1, A2, A3, A4, A5, A6)
OWNER B: (B1, B2, B3, B4, B5, B6)
…
Legal
HASH of any legal documentation.
Signatures
Community owners
Individual owners of each land 

Message validation

Union of outputs geometry needs to match the input region exactly
(insignificant math precision errors may need to be allowed)
Outputs geometry should not overlap one another
Signatures of community owners are required
Signatures for payments are required (if there are payments involved)

BN_LAND_MERGE

When land needs to be restructured it may make sense to merge pieces back into one piece owned by a single owner. This may not be necessary, at first, since pieces could just be transferred to new owner, but for mapping purposes and ease of use it may be needed at some point.


