# React Pattern Example — Metric Card

A small, predictable UI component demonstrating memoization discipline and clean prop contracts.

```tsx
import React, { useMemo } from 'react';

interface CardProps {
  title: string;
  value: number;
}

export function MetricCard({ title, value }: CardProps) {
  const formatted = useMemo(() => value.toLocaleString(), [value]);

  return (
    <div className='metric-card'>
      <h3>{title}</h3>
      <div>{formatted}</div>
    </div>
  );
}
```

Notes
• Minimal surface area for props
• Computations placed behind useMemo only where beneficial
• UI remains declarative and predictable
