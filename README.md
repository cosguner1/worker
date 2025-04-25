export default {
  async fetch(request, env, ctx) {
    let url = new URL(request.url);

    if (url.pathname.endsWith('.xml/')) {
      url.pathname = url.pathname.slice(0, -1);
      return Response.redirect(url.toString(), 301);
    }

    return fetch(request);
  }
}
