/*
 * TCSS 305
 * Assignment 2 - ShoppingCart
 */


package model;

import java.util.Objects;

/**
 * Class that stores info about a purchase order for a particular item.
 * 
 * @author davidshannon
 * @version 1
 */
public final class ItemOrder {

    // data fields:

    /** Item to be stored in the order. */
    private final Item myItem;

    /** Amount of the item to be stored. */
    private final int myQuantity;

    /**
     * Constructor for object that stores reference to item and the quantity of item
     * desired.
     * 
     * @param theItem is the item stored in the ItemOrder object.
     * @param theQuantity is the number of said item in the ItemOrder.
     */
    public ItemOrder(final Item theItem, final int theQuantity) {
        this.myItem = theItem;
        this.myQuantity = theQuantity;
    }

    /**
     * Method for returning the item in the particular ItemOrder.
     * 
     * @return the Item in the order.
     */
    public Item getItem() {
        return myItem;
    }

    /**
     * Method for returning the quantity of the item to be purchased.
     * 
     * @return the quantity of the specified item to be purchased.
     */
    public int getQuantity() {
        return myQuantity;
    }

    /**
     * Method for returning string representation of ItemOrder object.
     * 
     * @return the Item and quantity in the ItemOrder.
     */
    @Override
    public String toString() {
        return myItem + "(" + myQuantity + ")";
    }

    /**
     * Returns true if the parameter is an ItemOrder with the same item (myQuantity
     * ignored in this calculation to facilitate use of the equals method in
     * ShoppingCart class); false otherwise.
     * 
     * {@inheritDoc}
     */
    @Override
    public boolean equals(final Object theOther) {

        boolean result = false;
        if ((theOther != null) && (theOther.getClass() == this.getClass())) {
            final ItemOrder otherItemOrder = (ItemOrder) theOther;
            result = this.getItem().equals(otherItemOrder.getItem());
        }
        return result;
    }

    /**
     * Method that overrides hashCode from Object class.
     * 
     * @return hashCode value.
     */
    @Override
    public int hashCode() {
        return Objects.hash(getItem());
    }

}
