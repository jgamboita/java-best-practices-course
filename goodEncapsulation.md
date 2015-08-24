
```
/*
 * @(#)Person.java
 *
 * Copyright 2009 Telefónica I+D.
 */
package es.tid.bestpractices.encapsulation.good;

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class Person {

    private final List<Person> friends;
    private final List<Person> enemies;

    public Person() {
        friends = new ArrayList<Person>();
        enemies = new ArrayList<Person>();
    }

    public List<Person> getFriends() {
        return Collections.unmodifiableList(friends);
    }

    public List<Person> getEnemies() {
        return Collections.unmodifiableList(enemies);
    }

    public void addFriend(final Person friend) {

        if (!enemies.contains(friend))
            friends.add(friend);
        else
            throw new IllegalStateException("Person is already in enemies list!");
    }

    public void addEnemy(final Person enemy) {

        if (!friends.contains(enemy))
            enemies.add(enemy);
        else
            throw new IllegalStateException("Person is already in friends list!");
    }

    public static void main(String[] args) {

        final Person joe = new Person();
        final Person mike = new Person();

        final List<Person> joesFriends = joe.getFriends();
        joesFriends.add(mike); // Throws UnsupportedOperationException
        joe.addFriend(mike);
        joe.addEnemy(mike); // Throws IllegalStateException
    }
}
```