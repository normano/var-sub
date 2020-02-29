# var-sub

Bash style variable substitutions.

```typescript
await stringFromTemplateFile(__dirname + "/cloudfront.template.json", {
  VIEWER_REQUEST_FUNCTION_ARN: viewerRequestFunctionArn,
  ORIGIN_RESPONSE_FUNCTION_ARN: originResponseFunctionArn,
  CALLER_REFERENCE: callerReference,
  STAGE,
  CNAME
});
```

```typescript
await stringFromTemplate(`foo $BAR`, {
  BAR: "baz"
}); // foo baz

await stringFromTemplate("foo ${bar}", {
  BAR: "baz"
}); // foo baz

await stringFromTemplate("my home dir is $HOME", {
  ...process.env
}); // my home dir is /Users/joeflateau

await stringFromTemplate(
  await request.get("https://example.org/some/template"),
  {
    FOO: "bar"
  }
);
```
