
```

/*
 * @(#)Person.java
 *
 * Copyright 2009 Telefónica I+D.
 */
package es.tid.bestpractices.encapsulation.bad;

import java.util.ArrayList;
import java.util.List;

public class Person {

    private final List<Person> friends;
    private final List<Person> enemies;

    public Person() {
        friends = new ArrayList<Person>();
        enemies = new ArrayList<Person>();
    }

    public List<Person> getFriends() {
        return friends;
    }

    public List<Person> getEnemies() {
        return enemies;
    }

    public static void main(String[] args) {

        final Person joe = new Person();
        final Person mike = new Person();

        final List<Person> joesFriends = joe.getFriends();
        final List<Person> joesEnemies = joe.getEnemies();
        joesFriends.add(mike);
        joesEnemies.add(mike); //The same person shouldn't be a friend and enemy at the same time!
    }
}

```