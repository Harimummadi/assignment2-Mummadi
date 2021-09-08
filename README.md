# assignment2-Mummadi
# Hari Hara Mummadi
###### My Favourite place in the world is Ladakh located in India.
The best time to visit Ladakh is summer, I mostly like the **Adventurous Road-trip** on Bikes there in the snow and in between the mountains.Second comes the **Camping** and **Trekking** which are very famous and offers a plenty of plans like mountaineering,jeep safari,Hemis National Park. <br> The another important thing is **Magnetic Hill** which is famous for its scenic views and rough terrain,it is also known as Phenomenal Magnetic Hill- if we leave the vechile at hill's base and keep the brakes unlocked,slowly the vechile moves uphill without any support!<br> Apart from these I also love the White Water Rafting which is also named as **Grand Canyon of India**.
---
### Directions for Travelling from Maryville to Ladakh.
1. Book the Flight from Kansas City to Delhi,India.
2. Go to Kansas City from Maryville.
   1. Board the Flight in Kansas Airport-Missouri to Delhi-India.
   3. After Arrival at Delhi airport,we can take travel to ladakh by road or by flight.
      1. The best way to reach Ladakh is by road from Delhi so that we can enjoy the Nature and Ride.
1. Here we reached my favourite place Ladakh.
* If it is a Road trip carry an DSLR Camera.
* Good insulated boots or trekking shoes in winters. In summers, any sports shoes should be fine.
   * Sunglasses to protect your eyes from the reflections from snow.
   * To protect the skin from harsh sunlight,its better to carry a sunscreen lotion that has highest SPF.
* If Travelling on Bikes(really its an awesome adventure) check the vechile is in best condition.
   * Just Enjoy the Nature and have fun.
[Click here to read Aboutme](./AboutMe.md)
---
###  Food And Drinks
Here is the list of Food/Drink items which I would prefer.
| Item | Location | Amount |
|------|----------|------|
| Chicken Nuggets | Grill | $4 |
| Kit-Kat Ice cream Shake | IceMagic | $2.5 |
| Jalapeno Pizza | Mediterrian | $2.3 |
| Almond Milk | Mangolian | $1 |
---
### Pithy Quote
> "Be kind whenever possible. It is always possible."- *Dalai Lama* <br>
> "Every exit is an entry somewhere else."- *Tom Stoppard*.
---
### Code Fencing
> Convex hull of some given points is the intersection of all convex sets containing them. It is used as primary structure in many other problems in computational geometry and other areas like image processing, model identification, geographical data systems, and triangular computation of a set of points and so on. Computing the convex hull of a set of point is one of the most fundamental and important problems of computational geometry. In this paper a new algorithm is presented for computing the convex hull of a set of random points in the plane by using a sweep-line strategy. The sweep-line is a horizontal line that is moved from top to bottom on a map of points. Our algorithm is optimal and has time complexity O(nlogn) where n is the size of input.<br>
Link to the source <https://jac.ut.ac.ir/article_71276.html>
```
struct pt {
    double x, y;
};

bool cmp(pt a, pt b) {
    return a.x < b.x || (a.x == b.x && a.y < b.y);
}

bool cw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) < 0;
}

bool ccw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) > 0;
}

void convex_hull(vector<pt>& a) {
    if (a.size() == 1)
        return;

    sort(a.begin(), a.end(), &cmp);
    pt p1 = a[0], p2 = a.back();
    vector<pt> up, down;
    up.push_back(p1);
    down.push_back(p1);
    for (int i = 1; i < (int)a.size(); i++) {
        if (i == a.size() - 1 || cw(p1, a[i], p2)) {
            while (up.size() >= 2 && !cw(up[up.size()-2], up[up.size()-1], a[i]))
                up.pop_back();
            up.push_back(a[i]);
        }
        if (i == a.size() - 1 || ccw(p1, a[i], p2)) {
            while(down.size() >= 2 && !ccw(down[down.size()-2], down[down.size()-1], a[i]))
                down.pop_back();
            down.push_back(a[i]);
        }
    }

    a.clear();
    for (int i = 0; i < (int)up.size(); i++)
        a.push_back(up[i]);
    for (int i = down.size() - 2; i > 0; i--)
        a.push_back(down[i]);
}
```
Link for the Code Source <https://cp-algorithms.com/geometry/grahams-scan-convex-hull.html>


