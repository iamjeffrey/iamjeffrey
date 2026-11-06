
# JavaScript Web APIs

## URL Pattern API
Matches and extracts parameters from URLs using route-style syntax, 
the exact logic a router library does internally, available natively.

const pattern = new URLPattern({ pathname: "/products/:id" });
const match = pattern.exec("https://example.com/products/482");
console.log(match.pathname.groups.id); // "482"

Why it’s useful:
Genuinely useful for service workers deciding how to handle a fetch, 
or any code that needs route-matching logic without pulling in a full router

## Web Locks API
Coordinates access to a shared resource across multiple tabs, so two tabs don’t both try to, say,
 refresh the same auth token at the same time.

navigator.locks.request("token-refresh", async (lock) => {
  await refreshAuthToken();
});
Why it’s useful:

Solves a real cross-tab race condition that’s otherwise genuinely awkward to coordinate manually
Pairs naturally with Broadcast Channel from Part 2, one coordinates who does the work,
 the other announces the result

## Screen Orientation API
Reads the device’s current orientation and, on supporting devices, can lock it to a specific one.

console.log(screen.orientation.type); // "portrait-primary"
screen.orientation.addEventListener("change", () => {
  console.log("Orientation changed to", screen.orientation.type);
});
Why it’s useful:

Useful for games or media apps that need to react to, or enforce, a specific orientation

Limitations:
Reading orientation works everywhere; actually locking it is generally limited to mobile, 
and typically requires fullscreen mode first
