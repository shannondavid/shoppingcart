/*
 * TCSS 305
 * Assignment 2 - ShoppingCart
 */

package model;

import java.math.BigDecimal;
import java.util.ArrayList;
import java.util.List;
import java.util.ListIterator;

/**
 * Class that stores information about the shopping cart (total of all the Items
 * ordered and their quantity).
 * 
 * @author davidshannon
 * @version 1
 */
public class ShoppingCart {

    // data fields:

    /** List to hold Item Order in the shopping cart. */
    private final List<ItemOrder> myList;

    /** Boolean value to indicate if customer has membership or not. */
    private boolean myMembership;

    // constructor:

    /**
     * Constructor that creates an empty shopping cart.
     */
    public ShoppingCart() {
        myList = new ArrayList<ItemOrder>();
    }

    // methods:

    /**
     * Adds an order to the ArrayList, removing any previous order for an equivalent
     * item with the new order.
     * 
     * @param theOrder is the order to
     */
    public void add(final ItemOrder theOrder) {
        final ListIterator<ItemOrder> iterator = myList.listIterator();
        while (iterator.hasNext()) {
            if (iterator.next().equals(theOrder)) {
                iterator.remove();
            }
        }
        myList.add(theOrder);
    }

    /**
     * Method that sets membership status of the customer.
     * 
     * @param theMembership indicates whether or not customer has membership.
     */
    public void setMembership(final boolean theMembership) {
        this.myMembership = theMembership;
    }

    /**
     * Method that calculates the total cost of all items in the shopping cart.
     * 
     * @return The total cost of all the items in the shopping cart.
     */
    public BigDecimal calculateTotal() {
        BigDecimal cartTotal = new BigDecimal("0.0");
        for (final ItemOrder order : myList) {
            if (order.getItem().isBulk()
                && (order.getQuantity() >= order.getItem().getBulkQuantity())) {
                final int bulkQuant = order.getQuantity() / order.getItem().getBulkQuantity();
                final int remainder = order.getQuantity() % order.getItem().getBulkQuantity(); 
                cartTotal = cartTotal.add((BigDecimal.valueOf(bulkQuant).multiply
                                (order.getItem().getBulkPrice())).add
                                          (BigDecimal.valueOf(remainder).multiply
                                                          (order.getItem().getPrice()))); 
            } else {
                cartTotal = cartTotal.add(order.getItem().getPrice().multiply
                                (BigDecimal.valueOf(order.getQuantity())));
            }
        }
        //applies 15% discount to shopping cart total if shopper has store membership
        if (myMembership) {
            cartTotal = cartTotal.multiply(new BigDecimal(".85")); 
        }
        return cartTotal;
    }

    /** Method that removes all items from shopping cart. */
    public void clear() {
        myList.clear();
    }

    /**
     * Method builds a string representation of Shopping Cart using StringBuilder,
     * then returns a string representation of the StringBuilder.
     * 
     */
    @Override
    public String toString() {
        final StringBuilder output = new StringBuilder();
        for (final ItemOrder order : myList) {
            output.append(order);
            output.append("\n ");
        }
        return output.toString();
    }

}
