# RecyclerView

## [RecyclerView for displaying lists of data](https://developer.android.com/guide/topics/ui/layout/recyclerview#java)

1. RecyclerView makes it easy to efficiently display large sets of data. You supply the data and define how each item looks, and the RecyclerView library dynamically creates the elements when they're needed.

### Steps for implementing your RecyclerView

1. decide what the list or grid is going to look like. Ordinarily you'll be able to use one of the RecyclerView library's standard layout managers.
1. Design how each element in the list is going to look and behave. Based on this design, extend the `ViewHolder` class. Your version of `ViewHolder` provides all the functionality for your list items. Your view holder is a wrapper around a `View`, and that view is managed by RecyclerView.
1. Define the `Adapter` that associates your data with the `ViewHolder` views.

### Plan your layout

1. The RecyclerView library provides three layout managers, which handle the most common layout situations:
   - `LinearLayoutManager` arranges the items in a one-dimensional list.
   - `GridLayoutManager` arranges all items in a two-dimensional grid
   - `StaggeredGridLayoutManager` is similar to GridLayoutManager, but it does not require that items in a row have the same height (for vertical grids) or items in the same column have the same width (for horizontal grids).

### Implementing your adapter and view holder

1. When you define your adapter, you need to override three key methods
   - `onCreateViewHolder()`: `RecyclerView` calls this method whenever it needs to create a new `ViewHolder`. The method creates and initializes the ViewHolder and its associated View, but does not fill in the view's contents—the `ViewHolder` has not yet been bound to specific data.
   - `onBindViewHolder()`: `RecyclerView` calls this method to associate a `ViewHolder` with data. The method fetches the appropriate data and uses the data to fill in the view holder's layout.
   - `getItemCount()`: RecyclerView calls this method to get the size of the data set.