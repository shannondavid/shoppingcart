/*
 * TCSS 305 Assignment 2 - ShoppingCart
 */

package tests;

import static org.junit.Assert.assertEquals;
import static org.junit.Assert.assertFalse;
import static org.junit.Assert.assertNotEquals;

import java.awt.Color;
import java.math.BigDecimal;
import model.Item;
import org.junit.Before;
import org.junit.Test;

/**
 * Class to run JUnit Test on Item Class.
 * 
 * @author davidshannon
 * @version 1
 */
public class ItemTest {

    // The test fixture. The Object I will use in the tests.

    /**
     * An Item object to use in the tests.
     */
    private Item myItem;

    /**
     * A method to initialize the test fixture before each test.
     */
    @Before
    public void setUp() {
        myItem = new Item("Item", new BigDecimal("10.00"));
    }

    /**
     * Test of the non-bulk Item constructor.
     */
    @Test
    public void testNonBulkConstructor() {
        assertEquals("Item", myItem.getName());
        assertEquals(new BigDecimal("10.00"), myItem.getPrice());
        assertEquals(new BigDecimal("0.0"), myItem.getBulkPrice());
        assertEquals(0, myItem.getBulkQuantity());
        assertEquals(false, myItem.isBulk());
    }

    /**
     * Test of the bulk constructor.
     */
    @Test
    public void testBulkConstructor() {
        myItem = new Item("Item2", new BigDecimal("11.00"), 5, new BigDecimal("15.00"));
        assertEquals("Item2", myItem.getName());
        assertEquals(new BigDecimal("11.00"), myItem.getPrice());
        assertEquals(5, myItem.getBulkQuantity());
        assertEquals(new BigDecimal("15.00"), myItem.getBulkPrice());
        assertEquals(true, myItem.isBulk());
    }

    /**
     * Test of the simple constructor when myPrice is Null.
     */
    /*
     * @Test(expected = NullPointerException.class) public void testPriceNull() {
     * myItem = new Item("Item", null); }
     */

    /**
     * Test of the bulk Constructor when BulkPrice is Null.
     */
    /*
     * @Test(expected = NullPointerException.class) public void testBulkPriceNull()
     * { myItem = new Item("Item", new BigDecimal("1.00"), 1, null); }
     */

    /**
     * Test method for {@link Item#toString()}.
     */
    @Test
    public void testToStringBulk() {
        final Item item0 =
                        new Item("Item0", new BigDecimal("1.00"), 1, new BigDecimal("5.00"));
        assertEquals("Item0, $1.00 (1 for $5.00)", item0.toString());
    }

    /**
     * Test method for {@link Item#toString()}.
     */
    @Test
    public void testToStringNotBulk() {
        myItem = new Item("Item2", new BigDecimal("1.00"));
        assertEquals("Item2, $1.00", myItem.toString());
    }

    /**
     * Test of the equals() method.
     */
    @Test
    public void testEquals() {
        // an object is equal to itself - reflexive property
        assertEquals("equals() fails a test of the reflexive property.", myItem, myItem);

        // .equals() should return false if the parameter is null
        assertNotEquals("equals() fails to return false when passed a null parameter", myItem,
                        null);

        // .equals() should return false if the parameter is a different type
        assertNotEquals("equals() fails to return false when passed the wrong parameter type",
                        myItem, new Color(10, 20, 30));

        // the symmetric property should hold
        final Item item2 = new Item("Item", new BigDecimal("10.00"));
        assertEquals("equals() fails a test of the symmetric property.", myItem, item2);
        assertEquals("equals() fails a test of the symmetric property.", item2, myItem);

        // Items with different names should not be considered equal
        assertFalse("equals() fails to return false when names don't match.",
                    myItem.equals(new Item("abc", new BigDecimal("10.00"))));

        // Items with different prices should not be considered equal
        assertFalse("equals() fails to return false when prices don't match.",
                    myItem.equals(new Item("Item", new BigDecimal("24.24"))));

        final Item item3 =
                        new Item("Item", new BigDecimal("10.00"), 10, new BigDecimal("15.00"));
        // Items with different bulk prices should not be considered equal
        assertFalse("equals() fails to return false when bulk prices don't match.",
                    item3.equals(new Item("Item", new BigDecimal("10.00"), 10,
                                          new BigDecimal("20.00"))));

        // Items with different bulk quantities should not be considered equal
        assertFalse("equals() fails to return false when bulk quantities don't match.",
                    item3.equals(new Item("Item", new BigDecimal("10.00"), 15,
                                          new BigDecimal("15.00"))));
    }

    /**
     * Test method for {@link Point#toString()}.
     * 
     * /** Test of the hashCode() method.
     */
    @Test
    public void testHashCode() {
        // Equal objects should have equal hashCode values.
        final Item item2 = new Item("Item", new BigDecimal("10.00"));

        assertEquals("hashCode() fails to produce identical values for"
                     + " equal ImmutablePoints", myItem.hashCode(), item2.hashCode());
    }

}
