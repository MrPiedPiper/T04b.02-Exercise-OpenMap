This is the modified exercise T04b.02-Exercise-OpenMap. Modified by Napu Taitano/MrPiedPiper.


Here's what's different in a nutshell.
-----------------------------------------------------------------------

Instead of this,

        Uri.Builder uriBuilder = new Uri.Builder();
        uriBuilder.scheme("geo")
                .path("0,0")
                .query(address);
        Uri addressUri = uriBuilder.build();

-----------------------------------------------------------------------

I did this.

        Uri.Builder uriBuilder = new Uri.Builder();
        uriBuilder.scheme("geo")
                .appendPath("0,0")
                .appendQueryParameter("q", address);
        Uri addressUri = uriBuilder.build();

-----------------------------------------------------------------------

Apperently, you need to use .appendPath instead of append, and appendQueryParameter instead of query.


//Thanks to the folks at https://stackoverflow.com/questions/21689848/build-uri-of-the-format-xy for this info. (Mostly orodbhen, who wrote the answer I got this from.)