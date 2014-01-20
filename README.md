ZSBJson
=======

iOS-SBJson Extension for Null Handling

Some times we receive Null from our server for some JSON and SBJson Parser map Null -> NSNull.

For this reason our code become too much messy i.e, we have lot of NSNull checks. For example:

NSMutableDictionary *addressDictionary = [NSMutableDictionary dictionary];

   

    [addressDictionary setObject:isEmpty(self.

address)?[NSNull null]:self.address forKey:@"address"];

    [addressDictionary setObject:isEmpty(self.addressID)?[NSNull null]:self.addressID forKey:@"addressID"];

    [addressDictionary setObject:isEmpty(self.houseNo)?[NSNull null]:self.houseNo forKey:@"houseNo"];

    [addressDictionary setObject:isEmpty(self.postCode)?[NSNull null]:self.postCode forKey:@"postCode"];

    [addressDictionary setObject:isEmpty(self.townCity)?[NSNull null]:self.townCity forKey:@"townCity"];

And if we populate our model without applying NSNull checks our code leads to Crash in most of the times.

In order to avoid too much messy code we have an easy option by using SBJson extension that allow us to or not to map Null ->NSNull.By default its set not to have NSNull in our Dictionary.

Its very simple and we can use it in following way:

    SBJsonParser *parser=[[SBJsonParser alloc]init];//release

    parser.allowNSNull=YES; //No if we dont want to allow nulls

   

    result =  [parser objectWithString:

responseString];

 

You can download the code from following link.

 

https://github.com/zaigham1/ZSBJson

