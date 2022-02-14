# nullObjectPattern

```js
import Subscription from '../Subscription.js';
import User from '../User.js';
 
const user1 = new User('vasya@email.com', new Subscription('premium'));
user1.getCurrentSubscription().hasPremiumAccess(); // true
user1.getCurrentSubscription().hasProfessionalAccess(); // false
 
const user2 = new User('vasya@email.com', new Subscription('professional'));
user2.getCurrentSubscription().hasPremiumAccess(); // false
user2.getCurrentSubscription().hasProfessionalAccess(); // true
 
// Внутри создается фейковая, потому что подписка не передается
const user3 = new User('vasya@email.com');
user3.getCurrentSubscription().hasPremiumAccess(); // false
user3.getCurrentSubscription().hasProfessionalAccess(); // false
 
const user4 = new User('rakhim@hexlet.io'); // администратор, проверяется по емейлу
user4.getCurrentSubscription().hasPremiumAccess(); // true
user4.getCurrentSubscription().hasProfessionalAccess(); // true
```
