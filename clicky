// Golden Cookie Clicker
// By RainSlide, adapted by angel.cvnt
// Automatically click golden cookies and reindeers, WILL click wrath cookies.
// Version 1.0
// Updated 2023-11-08

// Cookie Clicker: https://orteil.dashnet.org/cookieclicker/

"use strict";

if (typeof Game !== "object" || Game === null || !Array.isArray(Game.shimmers)) {

	console.error(
		"Golden Cookie Clicker: Cookie Clicker API is not ready or invalid.\n" +
		"Please make sure you are running this script on a Cookie Clicker webpage, " +
		"and the page is fully loaded."
	);

} else if (typeof Proxy !== "function") {

	console.error(
		"Golden Cookie Clicker: JavaScript Proxy API is not available, " +
		"either update your browser, or use the ES3 compatible version:\n"+
		"https://rainslide.neocities.org/cookieclicker/GoldenCookieClicker.es3.js"
	);

} else {

	const apply = (target, _this, args) => {
		var shimmer = args[0];
		if ((shimmer.type === "golden") || shimmer.type === "reindeer") {
			setTimeout(() => shimmer.pop(), 500);
		}
		return Reflect.apply(target, _this, args);
	};

	Object.defineProperty(Game.shimmers, "push", {
		value: new Proxy(Game.shimmers.push, { apply }),
		writable: true,
		enumerable: false,
		configurable: true
	});

	typeof Game.Win === "function" &&
	Game.Win("Third-party");


}
